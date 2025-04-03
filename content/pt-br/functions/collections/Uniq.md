---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.Uniq
description: Returns the given collection, removing duplicate elements.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [uniq]
    returnType: any
    signatures: [collections.Uniq COLLECTION]
aliases: [/functions/uniq]
---

```go-html-template
{{ slice 1 3 2 1 | uniq }} → [1 3 2]
```
