---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Truncate
description: Returns the result of rounding TIME down to a multiple of DURATION since January 1, 0001, 00:00:00 UTC.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [TIME.Truncate DURATION]
---

The `Truncate` method operates on TIME as an absolute duration since the [zero time](g); it does not operate on the presentation form of the time. If DURATION is a multiple of one hour, `Truncate` may return a time with a non-zero minute, depending on the time zone.

```go-html-template
{{ $t := time.AsTime "2023-01-27T23:44:58-08:00" }}
{{ $d := time.ParseDuration "1h"}}

{{ ($t.Truncate $d).Format "2006-01-02T15:04:05-00:00" }} → 2023-01-27T23:00:00-00:00
```
