---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Split
description: Returns a slice of strings by splitting the given string by a delimiter.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [split]
    returnType: '[]string'
    signatures: [strings.Split STRING DELIM]
aliases: [/functions/split]
---

Examples:

```go-html-template
{{ split "tag1,tag2,tag3" "," }} → ["tag1", "tag2", "tag3"]
{{ split "abc" "" }} → ["a", "b", "c"]
```

> [!note]
> The `strings.Split` function essentially does the opposite of the [`collections.Delimit`] function. While `split` creates a slice from a string, `delimit` creates a string from a slice.

[`collections.Delimit`]: /functions/collections/delimit/
