---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: UnixMicro
description: Returns the given time.Time value expressed as the number of microseconds elapsed since January 1, 1970 UTC.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int64
    signatures: [TIME.UnixMicro]
---

See [Unix epoch](https://en.wikipedia.org/wiki/Unix_time).

```go-html-template
{{ $t := time.AsTime "2023-01-27T23:44:58-08:00" }}
{{ $t.UnixMicro }} → 1674891898000000
```
