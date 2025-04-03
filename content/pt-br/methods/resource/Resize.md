---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Resize
description: Applicable to images, returns an image resource resized to the given width and/or height.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: images.ImageResource
    signatures: [RESOURCE.Resize SPEC]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

Resize an image to the given width and/or height.

If you specify both width and height, the resulting image will be disproportionally scaled unless the original image has the same aspect ratio.

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with .Resize "300x" }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

{{% include "/_common/methods/resource/processing-spec.md" %}}

## Example

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with .Resize "300x webp q85 lanczos" }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Process"
  filterArgs="resize 300x webp q85 lanczos"
  example=true
>}}
