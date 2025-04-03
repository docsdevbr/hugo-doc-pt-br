---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: resources.Copy
description: Copies the given resource to the target path.
categories: []
params:
  functions_and_methods:
    aliases: []
    returnType: resource.Resource
    signatures: [resources.Copy TARGETPATH RESOURCE]
---

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ with resources.Copy "img/new-image-name.jpg" . }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

The relative URL of the new published resource will be:

```text
/img/new-image-name.jpg
```

> [!note]
> Use the `resources.Copy` function with global, page, and remote resources.
