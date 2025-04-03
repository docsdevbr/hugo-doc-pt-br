---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.GaussianBlur
description: Returns an image filter that applies a gaussian blur to an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.GaussianBlur SIGMA]
---

The sigma value must be positive, and indicates how much the image will be blurred. The blur-affected radius is approximately 3 times the sigma value.

## Usage

Create the filter:

```go-html-template
{{ $filter := images.GaussianBlur 5 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="GaussianBlur"
  filterArgs="5"
  example=true
>}}
