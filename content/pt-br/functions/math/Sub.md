---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: math.Sub
description: Subtracts one or more numbers from the first number.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [sub]
    returnType: any
    signatures: [math.Sub VALUE VALUE...]
---

If one of the numbers is a [`float`](g), the result is a `float`.

```go-html-template
{{ sub 12 3 2 }} → 7
```
