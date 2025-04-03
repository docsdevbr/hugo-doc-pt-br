---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Name
description: Returns the `name` property of the given menu entry.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [MENUENTRY.Name]
---

If you define the menu entry [automatically], the `Name` method returns the page's [`LinkTitle`], falling back to its [`Title`].

If you define the menu entry [in front matter] or [in site configuration], the `Name` method returns the `name` property of the given menu entry. If the `name` is not defined, and the menu entry resolves to a page, the `Name` returns the page [`LinkTitle`], falling back to its [`Title`].

[`LinkTitle`]: /methods/page/linktitle/
[`Title`]: /methods/page/title/
[automatically]: /content-management/menus/#define-automatically
[in front matter]: /content-management/menus/#define-in-front-matter
[in site configuration]: /content-management/menus/#define-in-site-configuration

```go-html-template
<ul>
  {{ range .Site.Menus.main }}
    <li><a href="{{ .URL }}">{{ .Name }}</a></li>
  {{ end }}
</ul>
```
