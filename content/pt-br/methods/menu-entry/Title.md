---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Title
description: Returns the `title` property of the given menu entry.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [MENUENTRY.Title]
---

The `Title` method returns the `title` property of the given menu entry. If the `title` is not defined, and the menu entry resolves to a page, the `Title` returns the page [`Title`].

[`Title`]: /methods/page/title/

```go-html-template
<ul>
  {{ range .Site.Menus.main }}
    <li><a href="{{ .URL }}" title="{{ .Title }}>{{ .Name }}</a></li>
  {{ end }}
</ul>
```
