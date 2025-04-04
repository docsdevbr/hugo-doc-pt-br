---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.Delimit
description: Loops through any array, slice, or map and returns a string of all the values separated by a delimiter.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [delimit]
    returnType: string
    signatures: ['collections.Delimit COLLECTION DELIMITER [LAST]']
aliases: [/functions/delimit]
---

Delimit a slice:

```go-html-template
{{ $s := slice "b" "a" "c" }}
{{ delimit $s ", " }} → b, a, c
{{ delimit $s ", " " and "}} → b, a and c
```

Delimit a map:

> [!note]
> The `delimit` function sorts maps by key, returning the values.

```go-html-template
{{ $m := dict "b" 2 "a" 1 "c" 3 }}
{{ delimit $m ", " }} → 1, 2, 3
{{ delimit $m ", " " and "}} → 1, 2 and 3
```
