---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: compare.Eq
description: Returns the boolean truth of arg1 == arg2 || arg1 == arg3.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [eq]
    returnType: bool
    signatures: ['compare.Eq ARG1 ARG2 [ARG...]']
aliases: [/functions/eq]
---

```go-html-template
{{ eq 1 1 }} → true
{{ eq 1 2 }} → false

{{ eq 1 1 1 }} → true
{{ eq 1 1 2 }} → true
{{ eq 1 2 1 }} → true
{{ eq 1 2 2 }} → false
```

You can also use the `compare.Eq` function to compare strings, boolean values, dates, slices, maps, and pages.
