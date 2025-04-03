---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: UTC
description: Returns the given time.Time value with the location set to UTC.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [TIME.UTC]
---

```go-html-template
{{ $t := time.AsTime "2023-01-27T23:44:58-08:00" }}
{{ $t.UTC }} → 2023-01-28 07:44:58 +0000 UTC
