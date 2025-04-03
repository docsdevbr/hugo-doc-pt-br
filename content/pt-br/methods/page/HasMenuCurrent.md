---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: HasMenuCurrent
description: Reports whether the given Page object matches the Page object associated with one of the child menu entries under the given menu entry in the given menu.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [PAGE.HasMenuCurrent MENU MENUENTRY]
aliases: [/functions/hasmenucurrent]
---

If the `Page` object associated with the menu entry is a section, this method also returns `true` for any descendant of that section.

```go-html-template
{{ $currentPage := . }}
{{ range site.Menus.main }}
  {{ if $currentPage.IsMenuCurrent .Menu . }}
    <a class="active" aria-current="page" href="{{ .URL }}">{{ .Name }}</a>
  {{ else if $currentPage.HasMenuCurrent .Menu . }}
    <a class="ancestor" aria-current="true" href="{{ .URL }}">{{ .Name }}</a>
  {{ else }}
    <a href="{{ .URL }}">{{ .Name }}</a>
  {{ end }}
{{ end }}
```

See [menu templates] for a complete example.

> [!note]
> When using this method you must either define the menu entry in front matter, or specify a `pageRef` property when defining the menu entry in your site configuration.

[menu templates]: /templates/menu/#example
