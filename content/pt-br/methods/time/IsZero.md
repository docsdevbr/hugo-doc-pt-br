---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: IsZero
description: Reports whether the given time.Time value represents the zero time instant, January 1, year 1, 00:00:00 UTC.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [TIME.IsZero]
---

````go-html-template
{{ $t1 := time.AsTime "2023-01-01T00:00:00-08:00" }}
{{ $t2 := time.AsTime "0001-01-01T00:00:00-00:00" }}

{{ $t1.IsZero }} → false
{{ $t2.IsZero }} → true
```
