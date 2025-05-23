---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Substr
description: Returns a substring of the given string, beginning with the start position and ending after the given length.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [substr]
    returnType: string
    signatures: ['strings.Substr STRING [START] [LENGTH]']
aliases: [/functions/substr]
---

The start position is zero-based, where `0` represents the first character of the string. If START is not specified, the substring will begin at position `0`. Specify a negative START position to extract characters from the end of the string.

If LENGTH is not specified, the substring will include all characters from the START position to the end of the string. If negative, that number of characters will be omitted from the end of string.

```go-html-template
{{ substr "abcdef" 0 }} → abcdef
{{ substr "abcdef" 1 }} → bcdef

{{ substr "abcdef" 0 1 }} → a
{{ substr "abcdef" 1 1 }} → b

{{ substr "abcdef" 0 -1 }} → abcde
{{ substr "abcdef" 1 -1 }} → bcde

{{ substr "abcdef" -1 }} → f
{{ substr "abcdef" -2 }} → ef

{{ substr "abcdef" -1 1 }} → f
{{ substr "abcdef" -2 1 }} → e

{{ substr "abcdef" -3 -1 }} → de
{{ substr "abcdef" -3 -2 }} → d
```
