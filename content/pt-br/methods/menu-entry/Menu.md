---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Menu
description: Returns the identifier of the menu that contains the given menu entry.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [MENUENTRY.Menu]
---

```go-html-template
{{ range .Site.Menus.main }}
  {{ .Menu }} → main
{{ end }}
```

Use this method with the [`IsMenuCurrent`] and [`HasMenuCurrent`] methods on a `Page` object to set "active" and "ancestor" classes on a rendered entry. See [this example].

[`HasMenuCurrent`]: /methods/page/hasmenucurrent/
[`IsMenuCurrent`]: /methods/page/ismenucurrent/
[this example]: /templates/menu/#example
