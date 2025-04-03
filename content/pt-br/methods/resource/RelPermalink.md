---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: RelPermalink
description: Publishes the given resource and returns its relative permalink.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [RESOURCE.RelPermalink]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

The `Permalink` method on a `Resource` object writes the resource to the publish directory, typically `public`, and returns its [relative permalink](g).

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .RelPermalink }} → /images/a.jpg
{{ end }}
```
