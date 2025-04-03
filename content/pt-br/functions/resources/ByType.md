---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: resources.ByType
description: Returns a collection of global resources of the given media type, or nil if none found.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: resource.Resources
    signatures: [resources.ByType MEDIATYPE]
---

The [media type] is typically one of `image`, `text`, `audio`, `video`, or `application`.

```go-html-template
{{ range resources.ByType "image" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
{{ end }}
```

> [!note]
> This function operates on global resources. A global resource is a file within the `assets` directory, or within any directory mounted to the `assets` directory.
>
> For page resources, use the [`Resources.ByType`] method on a `Page` object.

[`Resources.ByType`]: /methods/page/resources/
[media type]: https://en.wikipedia.org/wiki/Media_type
