---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.CountRunes
description: Returns the number of runes in the given string excluding whitespace.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [countrunes]
    returnType: int
    signatures: [strings.CountRunes INPUT]
aliases: [/functions/countrunes]
---

In contrast with the [`strings.RuneCount`] function, which counts every rune in a string, `strings.CountRunes` excludes whitespace.

```go-html-template
{{ "Hello, 世界" | strings.CountRunes }} → 8
```

[`strings.RuneCount`]: /functions/strings/runecount/
