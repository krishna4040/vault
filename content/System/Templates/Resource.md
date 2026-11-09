---
publish: true
created: 2026-10-15T16:16:14.669Z
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - resource
  - template
title:
description:
author:
reference:
project:
type:
---

<%await tp.file.move("Resources/PARA")%>
<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
const file = tp.file.find\_tfile(tp.file.path(true));

```
const title = await tp.system.prompt("Resource Title:");

// Find project notes
const projectFiles = tp.app.vault.getMarkdownFiles().filter(f => {
    const cache = tp.app.metadataCache.getFileCache(f);
    const tags = tp.obsidian.getAllTags(cache) ?? [];
    return tags.includes("#project") && !tags.includes("#template");
});

// Searchable picker: select a project note
const projectFile = await tp.system.suggester(
    f => f.basename,
    projectFiles,
    false,
    "Search projects..."
);

if (!projectFile) return;

const type = await tp.system.suggester(
	item => item,
	["literature", "permanent"]
);

let tags = await tp.system.prompt(
    "Tags:", "resource,", false, true
);

tags = (tags ?? "")
    .split(",")
    .map(tag => tag.trim())
    .filter(tag => tag !== "");

const date = tp.date.now();

await tp.app.fileManager.processFrontMatter(file, fm => {
    fm.tags = tags;
    fm.title = title;
    fm.created = date;
    fm.project = `[[${projectFile.path.replace(/\.md$/, "")}]]`;
    fm.type = type;
});
```

});
%>
