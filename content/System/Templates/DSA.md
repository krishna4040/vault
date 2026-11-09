---
publish: true
created: 2026-10-15T16:16:14.669Z
modified: 2026-10-15T16:16:14.669Z
published: 2026-10-15T16:16:14.669Z
tags:
  - resource
  - template
  - dsa
title:
description:
author:
reference:
project:
  - - Projects/DSA|DSA
lecture:
type: permanent
---

<%await tp.file.move("Resources/PARA")%>
<%\*
tp.hooks.on\_all\_templates\_executed(async () => {\
const file = tp.file.find\_tfile(tp.file.path(true));\
let title = await tp.system.prompt("Resource Title:")
let description = await tp.system.prompt("Description:")
let lecture = await tp.system.prompt("lecture:")
let date = await tp.date.now()
let type = await tp.system.prompt("Type of DSA Note:")

await tp.app.fileManager.processFrontMatter(file,(frontmatter) => {\
frontmatter.description = description
frontmatter.tags = frontmatter.tags.filter(tag => tag != 'template')
frontmatter.tags.push(type)
frontmatter.title = title
frontmatter.created = date
frontmatter.lecture = parseInt(lecture, 10)
});
});
%>
