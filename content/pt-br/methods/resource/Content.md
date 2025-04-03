---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Content
description: Returns the content of the given resource.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: any
    signatures: [RESOURCE.Content]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

The `Content` method on a `Resource` object returns `template.HTML` when the resource type is `page`, otherwise it returns a `string`.

[resource type]: /methods/resource/resourcetype/

```text {file="assets/quotations/kipling.txt"}
He travels the fastest who travels alone.
```

To get the content:

```go-html-template
{{ with resources.Get "quotations/kipling.txt" }}
  {{ .Content }} → He travels the fastest who travels alone.
{{ end }}
```

To get the size in bytes:

```go-html-template
{{ with resources.Get "quotations/kipling.txt" }}
  {{ .Content | len }} → 42
{{ end }}
```

To create an inline image:

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  <img src="data:{{ .MediaType.Type }};base64,{{ .Content | base64Encode }}">
{{ end }}
```

To create inline CSS:

```go-html-template
{{ with resources.Get "css/style.css" }}
  <style>{{ .Content | safeCSS }}</style>
{{ end }}
```

To create inline JavaScript:

```go-html-template
{{ with resources.Get "js/script.js" }}
  <script>{{ .Content | safeJS }}</script>
{{ end }}
```
