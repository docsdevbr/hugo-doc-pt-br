---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: compare.Le
description: Returns the boolean truth of arg1 <= arg2 && arg1 <= arg3.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [le]
    returnType: bool
    signatures: ['compare.Le ARG1 ARG2 [ARG...]']
aliases: [/functions/le]
---

```go-html-template
{{ le 1 1 }} → true
{{ le 1 2 }} → true
{{ le 2 1 }} → false

{{ le 1 1 1 }} → true
{{ le 1 1 2 }} → true
{{ le 1 2 1 }} → true
{{ le 1 2 2 }} → true

{{ le 2 1 1 }} → false
{{ le 2 1 2 }} → false
{{ le 2 2 1 }} → false
```

Use the `compare.Le` function to compare other data types as well:

```go-html-template
{{ le "ab" "a" }} → false
{{ le time.Now (time.AsTime "1964-12-30") }} → false
{{ le true false }} → false
```
