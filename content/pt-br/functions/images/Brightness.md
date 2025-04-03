---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.Brightness
description: Returns an image filter that changes the brightness of an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.Brightness PERCENTAGE]
---

The percentage must be in the range [-100, 100] where 0 has no effect. A value of `-100` produces a solid black image, and a value of `100` produces a solid white image.

## Usage

Create the image filter:

```go-html-template
{{ $filter := images.Brightness 12 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="Brightness"
  filterArgs="12"
  example=true
>}}
