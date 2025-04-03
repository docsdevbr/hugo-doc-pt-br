---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: ByWeight
description: Returns the given page collection sorted by weight in ascending order.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Pages
    signatures: [PAGES.ByWeight]
---

Assign a [weight](g) to a page using the `weight` field in front matter. The weight must be a non-zero integer. Lighter items float to the top, while heavier items sink to the bottom. Unweighted or zero-weighted pages are placed at the end of the collection.

```go-html-template
{{ range .Pages.ByWeight }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

To sort in descending order:

```go-html-template
{{ range .Pages.ByWeight.Reverse }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```
