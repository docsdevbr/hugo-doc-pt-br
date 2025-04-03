---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Sigmoid
description: Returns an image filter that changes the contrast of an image using a sigmoidal function.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Sigmoid MIDPOINT FACTOR]
---

This is a non-linear contrast change useful for photo adjustments; it preserves highlight and shadow detail.

The midpoint is the midpoint of contrast. It must be in the range [0, 1], typically 0.5.

The factor indicates how much to increase or decrease the contrast, typically in the range [-10, 10] where 0 has no effect. A positive value increases contrast, while a negative value decrease contrast.

## Usage

Create the filter:

```go-html-template
{{ $filter := images.Sigmoid 0.6 -4 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Sigmoid"
  filterArgs="0.6,-4"
  example=true
>}}
