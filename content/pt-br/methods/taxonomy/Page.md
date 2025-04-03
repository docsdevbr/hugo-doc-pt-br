---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Page
description: Returns the taxonomy page or nil if the taxonomy has no terms.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Page
    signatures: [TAXONOMY.Page]
---

{{< new-in 0.125.0 />}}

This `TAXONOMY` method returns nil if the taxonomy has no terms, so you must code defensively:

```go-html-template
{{ with .Site.Taxonomies.tags.Page }}
  <a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a>
{{ end }}
```

This is rendered to:

```html
<a href="/tags/">Tags</a>
```
