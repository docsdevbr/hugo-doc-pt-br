---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Count
description: Returns the number of non-overlapping instances of the given substring within the given string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: int
    signatures: [strings.Count SUBSTR STRING]
aliases: [/functions/strings.count]
---

If `SUBSTR` is an empty string, this function returns 1 plus the number of Unicode code points in `STRING`.

```go-html-template
{{ "aaabaab" | strings.Count "a" }} → 5
{{ "aaabaab" | strings.Count "aa" }} → 2
{{ "aaabaab" | strings.Count "aaa" }} → 1
{{ "aaabaab" | strings.Count "" }} → 8
```
