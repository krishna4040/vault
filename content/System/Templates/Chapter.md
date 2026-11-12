---
publish: true
created:
modified: 2026-11-12T16:42:05.745Z
published: 2026-11-12T16:42:05.745Z
tags:
  - resource
  - chapter
chapter_number:
chapter_title:
book:
page_start:
page_end:
page_length:
---

# Executive Summary

# Highlights

> [!quote] P1

**Takeaway**

---

# Navigation

```tabs
tab: Back
| File | Title | tags |
| ---- | ----- | ---- |

tab: Next
| File | Title | tags |
| ---- | ----- | ---- |

```

<%await tp.file.move("Resources/PARA")%>
<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
const file = tp.file.find\_tfile(tp.file.path(true));

```
const number = await tp.system.prompt("Chapter Number:");
const title = await tp.system.prompt("Chapter Title:");
const page_start = await tp.system.prompt("Enter Start Page Index:");
const page_end = await tp.system.prompt("Enter End Page Index:");

// Find project notes
const bookFiles = tp.app.vault.getMarkdownFiles().filter(f => {
    const cache = tp.app.metadataCache.getFileCache(f);
    const tags = tp.obsidian.getAllTags(cache) ?? [];
    return tags.includes("#book") && !tags.includes("#template");
});

// Searchable picker: select a project note
const book = await tp.system.suggester(
    f => f.basename,
    bookFiles,
    false,
    "Search books..."
);

if (!book) return;

let tags = await tp.system.prompt(
    "Tags:", "resource,chapter,", false, true
);

tags = (tags ?? "")
    .split(",")
    .map(tag => tag.trim())
    .filter(tag => tag !== "");

const date = tp.date.now();

await tp.app.fileManager.processFrontMatter(file, fm => {
    fm.tags = tags;
    fm.chapter_title = title;
	fm.chapter_number = parseInt(number);
    fm.created = date;
    fm.book = `[[${book.path.replace(/\.md$/, "")}]]`;
	fm.page_start = parseInt(page_start);
	fm.page_end = parseInt(page_end);
	fm.chapter_length = fm.page_end - fm.page_start;
});
```

});
%>
