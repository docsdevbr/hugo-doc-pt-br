---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Reverse
description: Returns the given menu, reversing the sort order of its entries.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: navigation.Menu
    signatures: [MENU.Reverse]
---

The `Reverse` method returns the given menu, reversing the sort order of its entries.

Consider this menu definition:

{{< code-toggle file=hugo >}}
[[menus.main]]
name = 'Services'
pageRef = '/services'
weight = 10

[[menus.main]]
name = 'About'
pageRef = '/about'
weight = 20

[[menus.main]]
name = 'Contact'
pageRef = '/contact'
weight = 30
{{< /code-toggle >}}

To sort the entries by name in descending order:

```go-html-template
<ul>
  {{ range .Site.Menus.main.ByName.Reverse }}
    <li><a href="{{ .URL }}">{{ .Name }}</a></li>
  {{ end }}
</ul>
```

Hugo renders this to:

```html
<ul>
  <li><a href="/services/">Services</a></li>
  <li><a href="/contact">Contact</a></li>
  <li><a href="/about/">About</a></li>
</ul>
```
