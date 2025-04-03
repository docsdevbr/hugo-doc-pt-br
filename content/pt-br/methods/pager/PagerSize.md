---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: PagerSize
description: Returns the number of pages per pager.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [PAGER.PagerSize]
---

{{< new-in 0.128.0 />}}

The number of pages per pager is determined by the optional second argument passed to the [`Paginate`] method, falling back to the `pagerSize` as defined in your [site configuration].

[`Paginate`]: /methods/page/paginate/
[site configuration]: /templates/pagination/#configuration

```go-html-template
{{ $pages := where site.RegularPages "Type" "posts" }}
{{ $paginator := .Paginate $pages }}

{{ range $paginator.Pages }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}

{{ with $paginator }}
  {{ .PagerSize }}
{{ end }}
```
