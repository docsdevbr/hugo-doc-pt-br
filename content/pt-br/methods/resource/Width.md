---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Width
description: Applicable to images, returns the width of the given resource.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [RESOURCE.Width]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .Width }} → 600
{{ end }}
```

Use the `Width` and `Height` methods together when rendering an `img` element:

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}">
{{ end }}
```
