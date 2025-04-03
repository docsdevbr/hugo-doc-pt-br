---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.Apply
description: Returns a new collection with each element transformed by the given function.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [apply]
    returnType: '[]any'
    signatures: [collections.Apply COLLECTION FUNCTION PARAM...]
aliases: [/functions/apply]
---

The `apply` function takes three or more arguments, depending on the function being applied to the collection elements.

The first argument is the collection itself, the second argument is the function name, and the remaining arguments are passed to the function, with the string `"."` representing the collection element.

```go-html-template
{{ $s := slice "hello" "world" }}

{{ $s = apply $s "strings.FirstUpper" "." }}
{{ $s }} → [Hello World]

{{ $s = apply $s "strings.Replace" "." "l" "_" }}
{{ $s }} →  [He__o Wor_d]
```
