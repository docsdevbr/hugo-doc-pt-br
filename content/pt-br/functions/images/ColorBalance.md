---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.ColorBalance
description: Returns an image filter that changes the color balance of an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.ColorBalance PCTRED PCTGREEN PCTBLUE]
---

The percentage for each channel (red, green, blue) must be in the range [-100, 500].

## Usage

Create the filter:

```go-html-template
{{ $filter := images.ColorBalance -10 10 50 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="ColorBalance"
  filterArgs="-10,10,50"
  example=true
>}}
