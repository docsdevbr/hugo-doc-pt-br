---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.CountWords
description: Returns the number of words in the given string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [countwords]
    returnType: int
    signatures: [strings.CountWords INPUT]
aliases: [/functions/countwords]
---

```go-html-template
{{ "Hugo is a static site generator." | countwords }} → 6
```
