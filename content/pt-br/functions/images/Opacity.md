---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Opacity
description: Returns an image filter that changes the opacity of an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Opacity OPACITY]
---

{{< new-in 0.119.0 />}}

The opacity value must be in the range [0, 1]. A value of `0` produces a transparent image, and a value of `1` produces an opaque image (no transparency).

## Usage

Create the filter:

```go-html-template
{{ $filter := images.Opacity 0.65 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

The `images.Opacity` filter is most useful for target formats such as PNG and WebP that support transparency. If the source image does not support transparency, combine this filter with the `images.Process` filter:

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ $filters := slice
    (images.Opacity 0.65)
    (images.Process "png")
  }}
  {{ with . | images.Filter $filters }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Opacity"
  filterArgs="0.65"
  example=true
>}}
