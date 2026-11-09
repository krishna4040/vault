---
publish: true
created:
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - area
  - template
title:
cover:
status:
priority:
---

# Overview

- \[Name::{{Name}}]
- \[Description::{{Description}}]

# Goals / Outcomes

**Purpose (Primary Goal)**

> Why This Exists?

**Sub Goal**

- [ ] {{GOAL1}}
- [ ] {{GOAL2}}
- [ ] {{GOAL3}}

**Success Metrics (Checks)**

| Metric | Type | Current | Target | Cadence |
| ------ | ---- | ------- | ------ | ------- |
|        |      |         |        |         |

# Budget

# Projects

| File | Status | Priority |
| ---- | ------ | -------- |

<%await tp.file.move("Areas/PARA")%>

<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
try {
const file = tp.file.find\_tfile(tp.file.path(true));

```
    // Project details
    const title = await tp.system.prompt("Area Name:");
    if (title === null) return;

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

    // Cover image with retry logic
    let cover;

    while (true) {
        const query = await tp.system.prompt("Cover query:");
        if (query === null) return;

        try {
            const picture = await tp.web.random_picture(
                "1200x600",
                query
            );

            cover = picture.match(
                /!\[.*?\]\(<?(https?:\/\/.*?)(?:\)|\\\))/
            )?.[1];

            if (cover) break;

            new Notice(
                "Could not extract the cover URL. Try another query."
            );
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
    await tp.app.fileManager.processFrontMatter(
        file,
        (frontmatter) => {
            frontmatter.tags = tags;
            frontmatter.title = title;
            frontmatter.created = date;
            frontmatter.cover = cover;
            frontmatter.status = status;
            frontmatter.priority = priority;
        }
    );

    new Notice("Frontmatter updated successfully!");

} catch (error) {
    console.error("Project template error:", error);
    new Notice(`Project creation failed: ${error.message}`);
}
```

});
%>
