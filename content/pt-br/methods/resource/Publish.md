---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Publish
description: Publishes the given resource.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: nil
    signatures: [RESOURCE.Publish]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

The `Publish` method on a `Resource` object writes the resource to the publish directory, typically `public`.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .Publish }}
{{ end }}
```

The `Permalink` and `RelPermalink` methods also publish a resource. `Publish` is a convenience method for publishing without a return value. For example, this:

```go-html-template
{{ $resource.Publish }}
```

Instead of this:

```go-html-template
{{ $noop := $resource.Permalink }}
```
