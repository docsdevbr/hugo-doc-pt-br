---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: compare.Gt
description: Returns the boolean truth of arg1 > arg2 && arg1 > arg3.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [gt]
    returnType: bool
    signatures: ['compare.Gt ARG1 ARG2 [ARG...]']
aliases: [/functions/gt]
---

```go-html-template
{{ gt 1 1 }} → false
{{ gt 1 2 }} → false
{{ gt 2 1 }} → true

{{ gt 1 1 1 }} → false
{{ gt 1 1 2 }} → false
{{ gt 1 2 1 }} → false
{{ gt 1 2 2 }} → false

{{ gt 2 1 1 }} → true
{{ gt 2 1 2 }} → false
{{ gt 2 2 1 }} → false
```

Use the `compare.Gt` function to compare other data types as well:

```go-html-template
{{ gt "ab" "a" }} → true
{{ gt time.Now (time.AsTime "1964-12-30") }} → true
{{ gt true false }} → true
```
