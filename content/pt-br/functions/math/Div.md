---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: math.Div
description: Divides the first number by one or more numbers.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [div]
    returnType: any
    signatures: [math.Div VALUE VALUE...]
---

If one of the numbers is a [`float`](g), the result is a `float`.

```go-html-template
{{ div 12 3 2 }} → 2
```
