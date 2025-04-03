---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.AutoOrient
description: Returns an image filter that rotates and flips an image as needed per its EXIF orientation tag.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.AutoOrient]
---

{{< new-in 0.121.2 />}}

## Usage

Create the filter:

```go-html-template
{{ $filter := images.AutoOrient }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

> [!note]
> When using with other filters, specify `images.AutoOrient` first.

```go-html-template
{{ $filters := slice
  images.AutoOrient
  (images.Process "resize 200x")
}}
{{ with resources.Get "images/original.jpg" }}
  {{ with images.Filter $filters . }}
    <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
  {{ end }}
{{ end }}
```

## Example

{{< img
  src="images/examples/landscape-exif-orientation-5.jpg"
  alt="Zion National Park"
  filter="AutoOrient"
  filterArgs=""
  example=true
>}}
