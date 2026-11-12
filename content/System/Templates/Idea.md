---
publish: true
created:
modified: 2026-11-12T16:42:05.745Z
published: 2026-11-12T16:42:05.745Z
title:
chapter:
order:
---

<%\*
await tp.file.move("Resources/Idea");

tp.hooks.on\_all\_templates\_executed(async () => {
const file = tp.file.find\_tfile(tp.file.path(true));

```
const title = await tp.system.prompt("Resource Title:");
if (title === null) return;

const order = await tp.system.prompt("Order Number:");
if (order === null) return;

const orderNumber = Number.parseInt(order, 10);
if (!Number.isFinite(orderNumber)) {
    new Notice("Invalid order number.");
    return;
}

const bookFiles = tp.app.vault.getMarkdownFiles().filter(f => {
    const cache = tp.app.metadataCache.getFileCache(f);
    const tags = tp.obsidian.getAllTags(cache) ?? [];
    return tags.includes("#book") && !tags.includes("#template");
});

const bookFile = await tp.system.suggester(
    f => f.basename,
    bookFiles,
    false,
    "Search books..."
);
if (!bookFile) return;

const bookPath = bookFile.path.replace(/\.md$/, "");

const chapterFiles = tp.app.vault.getMarkdownFiles().filter(f => {
    const cache = tp.app.metadataCache.getFileCache(f);
    const tags = tp.obsidian.getAllTags(cache) ?? [];
    const linkedBook = cache?.frontmatter?.book;

    if (!tags.includes("#chapter") || !linkedBook) return false;

    const linkedPath = String(linkedBook)
        .replace(/^\[\[/, "")
        .replace(/\]\]$/, "")
        .replace(/\.md$/, "");

    return linkedPath === bookPath;
});

if (chapterFiles.length === 0) {
    new Notice("No chapters found for this book.");
    return;
}

const chapterFile = await tp.system.suggester(
    f => f.basename,
    chapterFiles,
    false,
    "Search chapters..."
);
if (!chapterFile) return;

await tp.app.fileManager.processFrontMatter(file, fm => {
    fm.title = title;
    fm.created = tp.date.now();
    fm.order = orderNumber;
    fm.chapter = `[[${chapterFile.path.replace(/\.md$/, "")}]]`;
});
```

});
%>

---

# Connections
