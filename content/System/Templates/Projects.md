---
publish: true
created:
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - project
  - template
title:
description:
due:
cover:
status: active
area: area
priority: 3
---

# Overview

- \[Name::<%tp.frontmatter.title%>]
- \[Description::<%tp.frontmatter.description%>]
- \[Project Type::{{Type}}]

# Roadmap (Syllabus)

Detailed Roadmap

**Milestones**

**Success Metrics (Checks)**

| Metric          | Type    | Current | Target        | Cadence |
| --------------- | ------- | ------- | ------------- | ------- |
| Sprint Velocity | Process |         |               | 15 days |
| user signups    | Outcome | 0       | 100 per month | monthly |
| API response    | Outcome | 100ms   | 10ms          | monthly |

**Definition of Done**

> When this project is considered complete?

# Resources

<%await tp.file.move("Projects/PARA")%>

<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
try {
const file = tp.file.find\_tfile(tp.file.path(true));

```
    // Project details
    const title = await tp.system.prompt("Project Name:");
    if (title === null) return;

    // Pick an area note tagged #area
    const areaFiles = tp.app.vault.getMarkdownFiles().filter(f => {
        const cache = tp.app.metadataCache.getFileCache(f);
        const tags = tp.obsidian.getAllTags(cache) ?? [];

        return tags.includes("#area") && !tags.includes("#template");
    });

    if (areaFiles.length === 0) {
        new Notice("No notes tagged #area were found.");
        return;
    }

    const areaFile = await tp.system.suggester(
        f => f.basename,
        areaFiles,
        false,
        "Search areas..."
    );

    if (!areaFile) return;

    const tagInput = await tp.system.prompt(
        "Tags:",
        "project,",
        false,
        true
    );
    if (tagInput === null) return;

    const tags = tagInput
        .split(",")
        .map(tag => tag.trim())
        .filter(tag => tag !== "");

    // Dates
    const date = tp.date.now("YYYY-MM-DD");
    const today = window.moment(date, "YYYY-MM-DD", true);

    let parsedDue;

    while (true) {
        const due = await tp.system.prompt(
            "Enter due date:",
            "2026-"
        );

        if (due === null) return;

        parsedDue = window.moment(due, "YYYY-MM-DD", true);

        if (!parsedDue.isValid()) {
            new Notice("Invalid date. Use YYYY-MM-DD.");
            continue;
        }

        if (!parsedDue.isAfter(today, "day")) {
            new Notice("Due date must be greater than today's date.");
            continue;
        }

        break;
    }

    // Cover image with retry logic
    let cover;

    while (true) {
        const query = await tp.system.prompt("Cover query:");
        if (query === null) return;

        try {
            const picture = await tp.web.random_picture("1200x600", query);

            cover = picture.match(
                /!\[.*?\]\(<?(https?:\/\/.*?)(?:\)|\\\))/
            )?.[1];

            if (cover) break;

            new Notice("Could not extract the cover URL. Try another query.");
        } catch (error) {
            console.error("Cover error:", error);
            new Notice("Cover request failed. Please try again.");
        }
    }

    // Project status
    const status = await tp.system.suggester(
        item => item,
        ["active", "inactive"]
    );
    if (status === null) return;

    // Project priority
    const priority = await tp.system.suggester(
        item => item,
        [0, 1, 2, 3]
    );
    if (priority === null) return;

    // Update frontmatter
    await tp.app.fileManager.processFrontMatter(file, frontmatter => {
        frontmatter.tags = tags;
        frontmatter.title = title;

        // Store the selected area as a note link
        frontmatter.area = `[[${areaFile.path.replace(/\.md$/, "")}]]`;

        frontmatter.due = parsedDue.format("YYYY-MM-DD");
        frontmatter.created = date;
        frontmatter.cover = cover;
        frontmatter.status = status;
        frontmatter.priority = priority;
    });

    new Notice("Frontmatter updated successfully!");

} catch (error) {
    console.error("Project template error:", error);
    new Notice(`Project creation failed: ${error.message}`);
}
```

});
%>
