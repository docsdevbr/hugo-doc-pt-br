---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Abs
description: Returns the absolute value of the given time.Duration value.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Duration
    signatures: [DURATION.Abs]
---

```go-html-template
{{ $d = time.ParseDuration "-3h" }}
{{ $d.Abs }} → 3h0m0s
```
