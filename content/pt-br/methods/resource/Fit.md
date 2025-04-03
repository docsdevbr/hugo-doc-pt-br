---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Fit
description: Applicable to images, returns an image resource downscaled to fit the given dimensions while maintaining aspect ratio.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: images.ImageResource
    signatures: [RESOURCE.Fit SPEC]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

Downscale an image to fit the given dimensions while maintaining aspect ratio. You must provide both width and height.

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with .Fit "200x200" }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

{{% include "/_common/methods/resource/processing-spec.md" %}}

## Example

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with .Fit "300x175 webp q85 lanczos" }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Process"
  filterArgs="fit 300x175 webp q85 lanczos"
  example=true
>}}
