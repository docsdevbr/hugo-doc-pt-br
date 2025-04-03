---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: math.Min
description: Returns the smaller of all numbers. Accepts scalars, slices, or both.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: float64
    signatures: [math.Min VALUE...]
---

```go-html-template
{{ math.Min 1 (slice 2 3) 4 }} → 1
```
