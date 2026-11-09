---
publish: true
title: Lecture
created: 2025-03-10
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - resource
  - template
description:
author:
reference:
lecture:
type: literature
---

# Topic

---

# Follow up

```tabs
tab: Next Lectures
| File | created |
| ---- | ------- |

tab: Previous Lectures
| File | created |
| ---- | ------- |

```

---

<%await tp.file.move("Resources/PARA")%>

<%\*
tp.hooks.on\_all\_templates\_executed(async () => {
const file = tp.file.find\_tfile(tp.file.path(true));
let lecture = await tp.system.prompt("Lecture number:");
let title = await tp.system.prompt("Note name:")
let author = await tp.system.prompt("Author name:");
let tags = await tp.system.prompt("Tags:","index",false,true);
let date = tp.date.now()
tags = tags.split(",").map(tag => tag.trim()).filter(tag => tag != "");
await tp.app.fileManager.processFrontMatter(file,(frontmatter) => {
frontmatter.tags = tags
frontmatter.lecture = parseInt(lecture, 10)
frontmatter.title = title
frontmatter.created = date
});
});
%>
