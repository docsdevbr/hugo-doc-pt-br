---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: PageGroups
description: Returns the page groups in the current pager.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.PagesGroup
    signatures: [PAGER.PageGroups]
---

Use the `PageGroups` method with any of the [grouping methods].

[grouping methods]: /quick-reference/page-collections/#group

```go-html-template
{{ $pages := where site.RegularPages "Type" "posts" }}
{{ $paginator := .Paginate ($pages.GroupByDate "Jan 2006") }}

{{ range $paginator.PageGroups }}
  <h2>{{ .Key }}</h2>
  {{ range .Pages }}
    <h3><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h3>
  {{ end }}
{{ end }}

{{ template "_internal/pagination.html" . }}
```
