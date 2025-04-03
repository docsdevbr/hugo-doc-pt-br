---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Nanoseconds
description: Returns the time.Duration value as an integer nanosecond count.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int64
    signatures: [DURATION.Nanoseconds]
---

```go-html-template
{{ $d = time.ParseDuration "3.5h2.5m1.5s" }}
{{ $d.Nanoseconds }} → 12751500000000
```
