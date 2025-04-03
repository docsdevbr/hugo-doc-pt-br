---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Sub
description: Returns the duration computed by subtracting TIME2 from TIME1.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Duration
    signatures: [TIME1.Sub TIME2]
---

```go-html-template
{{ $t1 := time.AsTime "2023-01-27T23:44:58-08:00" }}
{{ $t2 := time.AsTime "2023-01-26T22:34:38-08:00" }}

{{ $t1.Sub $t2 }} → 25h10m20s
```
