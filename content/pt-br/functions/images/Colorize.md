---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Colorize
description: Returns an image filter that produces a colorized version of an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Colorize HUE SATURATION PERCENTAGE]
---

The hue is the angle on the color wheel, typically in the range [0, 360].

The saturation must be in the range [0, 100].

The percentage specifies the strength of the effect, and must be in the range [0, 100].

## Usage

Create the filter:

```go-html-template
{{ $filter := images.Colorize 180 50 20 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Colorize"
  filterArgs="180,50,20"
  example=true
>}}
