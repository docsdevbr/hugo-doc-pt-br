---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Add
description: Returns the given time plus the given duration.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [TIME.Add DURATION]
---

```go-html-template
{{ $t := time.AsTime "2023-01-27T23:44:58-08:00" }}

{{ $d1 = time.ParseDuration "3h20m10s" }}
{{ $d2 = time.ParseDuration "-3h20m10s" }}

{{ $t.Add $d1 }} → 2023-01-28 03:05:08 -0800 PST
{{ $t.Add $d2 }} → 2023-01-27 20:24:48 -0800 PST
```
