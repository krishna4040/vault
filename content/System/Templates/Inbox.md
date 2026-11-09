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
type: fleeting
---

# What I found

# Why I liked it

# My initial thought

<%await tp.file.move("Inbox/Fleeting")%>

<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
const file = tp.file.find\_tfile(tp.file.path(true));
const title = await tp.system.prompt("Title:");
const date = tp.date.now();

```
await tp.app.fileManager.processFrontMatter(file, fm => {
    fm.title = title;
    fm.created = date;
	fm.tags = fm.tags.filter(tag => tag !== "template")
});
```

});
%>
