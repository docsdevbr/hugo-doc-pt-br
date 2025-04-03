---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Grayscale
description: Returns an image filter that produces a grayscale version of an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Grayscale]
---

## Usage

Create the filter:

```go-html-template
{{ $filter := images.Grayscale }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Grayscale"
  filterArgs=""
  example=true
>}}
