---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Minutes
description: Returns the time.Duration value as a floating point number of minutes.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: float64
    signatures: [DURATION.Minutes]
---

```go-html-template
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Minutes }} → 212.525
```
