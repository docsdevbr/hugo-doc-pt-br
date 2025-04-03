---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.Plainify
description: Returns a string with all HTML tags removed.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [plainify]
    returnType: template.HTML
    signatures: [transform.Plainify INPUT]
aliases: [/functions/plainify]
---

```go-html-template
{{ "<b>BatMan</b>" | plainify }} → BatMan
```
