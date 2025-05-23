---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Mask
description: Returns an image filter that applies a mask to the source image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Mask RESOURCE]
---

{{< new-in 0.141.0 />}}

The `images.Mask` filter applies a mask to an image. Black pixels in the mask make the corresponding areas of the base image transparent, while white pixels keep them opaque. Color images are converted to grayscale for masking purposes. The mask is automatically resized to match the dimensions of the base image.

> [!note]
> Of the formats supported by Hugo's imaging pipeline, only PNG and WebP have an alpha channel to support transparency. If your source image has a different format and you require transparent masked areas, convert it to either PNG or WebP as shown in the example below.

When applying a mask to a non-transparent image format such as JPEG, the masked areas will be filled with the color specified by the `bgColor` parameter in your [site configuration]. You can override that color with a `Process` image filter:

```go-html-template
{{ $filter := images.Process "#00ff00" }}
```

## Usage

Create a slice of filters, one for WebP conversion and the other for mask application:

```go-html-template
{{ $filter1 := images.Process "webp" }}
{{ $filter2 := images.Mask (resources.Get "images/mask.png") }}
{{ $filters := slice $filter1 $filter2 }}
```

Apply the filters using the [`images.Filter`] function:

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with . | images.Filter $filters }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

You can also apply the filter using the [`Filter`] method on a 'Resource' object:

```go-html-template
{{ with resources.Get "images/original.jpg" }}
  {{ with .Filter $filters }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

## Example

Mask

{{< img
  src="images/examples/mask.png"
  example=false
>}}

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="mask"
  filterArgs="images/examples/mask.png"
  example=true
>}}

[`Filter`]: /methods/resource/filter/
[`images.Filter`]: /functions/images/filter/
[site configuration]: /configuration/imaging/
