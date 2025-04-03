---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Limit
description: Returns the given menu, limited to the first N entries.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: navigation.Menu
    signatures: [MENU.Limit N]
---

The `Limit` method returns the given menu, limited to the first N entries.

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

To sort the entries by name, and limit to the first 2 entries:

```go-html-template
<ul>
  {{ range .Site.Menus.main.ByName.Limit 2 }}
    <li><a href="{{ .URL }}">{{ .Name }}</a></li>
  {{ end }}
</ul>
```

Hugo renders this to:

```html
<ul>
  <li><a href="/about/">About</a></li>
  <li><a href="/contact">Contact</a></li>
</ul>
```
