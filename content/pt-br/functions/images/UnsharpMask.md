---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: images.UnsharpMask
description: Returns an image filter that sharpens an image.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: images.filter
    signatures: [images.UnsharpMask SIGMA AMOUNT THRESHOLD]
---

The sigma argument is used in a gaussian function and affects the radius of effect. Sigma must be positive. The sharpen radius is approximately 3 times the sigma value.

The amount argument controls how much darker and how much lighter the edge borders become. Typically between 0.5 and 1.5.

The threshold argument controls the minimum brightness change that will be sharpened. Typically between 0 and 0.05.

## Usage

Create the filter:

```go-html-template
{{ $filter := images.UnsharpMask 10 0.4 0.03 }}
```

{{% include "/_common/functions/images/apply-image-filter.md" %}}

## Example

{{< img
  src="images/examples/zion-national-park.jpg"
  alt="Zion National Park"
  filter="UnsharpMask"
  filterArgs="10,0.4,0.03"
  example=true
>}}
