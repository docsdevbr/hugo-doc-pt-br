---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Weight
description: Returns the `weight` property of the given menu entry.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [MENUENTRY.Weight]
---

If you define the menu entry [automatically], the `Weight` method returns the page's [`Weight`].

If you define the menu entry [in front matter] or [in site configuration], the `Weight` method returns the `weight` property, falling back to the page's `Weight`.

[`Weight`]: /methods/page/weight/
[automatically]: /content-management/menus/#define-automatically
[in front matter]: /content-management/menus/#define-in-front-matter
[in site configuration]: /content-management/menus/#define-in-site-configuration

In this contrived example, we limit the number of menu entries based on weight:

```go-html-template
<ul>
  {{ range .Site.Menus.main }}
    {{ if le .Weight 42 }}
      <li><a href="{{ .URL }}">{{ .Name }}</a></li>
    {{ end }}
  {{ end }}
</ul>
```
