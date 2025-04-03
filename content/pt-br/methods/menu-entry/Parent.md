---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Parent
description: Returns the `parent` property of the given menu entry.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [MENUENTRY.Parent]
---

With this menu definition:

{{< code-toggle file=hugo >}}
[[menus.main]]
name = 'Products'
pageRef = '/product'
weight = 10

[[menus.main]]
name = 'Product 1'
pageRef = '/products/product-1'
parent = 'Products'
weight = 1

[[menus.main]]
name = 'Product 2'
pageRef = '/products/product-2'
parent = 'Products'
weight = 2
{{< /code-toggle >}}

This template renders the nested menu, listing the `parent` property next each of the child entries:

```go-html-template
<ul>
  {{ range .Site.Menus.main }}
    <li>
      <a href="{{ .URL }}">{{ .Name }}</a>
      {{ if .HasChildren }}
        <ul>
          {{ range .Children }}
            <li><a href="{{ .URL }}">{{ .Name }}</a> ({{ .Parent }})</li>
          {{ end }}
        </ul>
      {{ end }}
    </li>
  {{ end }}
</ul>
```
