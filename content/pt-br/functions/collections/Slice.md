---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.Slice
description: Returns a slice composed of the given values.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [slice]
    returnType: any
    signatures: ['collections.Slice [VALUE...]']
aliases: [/functions/slice]
---

```go-html-template
{{ $s := slice "a" "b" "c" }}
{{ $s }} → [a b c]
```

To create an empty slice:

```go-html-template
{{ $s := slice }}
```
