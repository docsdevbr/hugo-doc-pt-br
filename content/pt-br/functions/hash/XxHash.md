---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: hash.XxHash
description: Returns the 64-bit xxHash non-cryptographic hash of the given string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [xxhash]
    returnType: string
    signatures: [hash.XxHash STRING]
---

```go-html-template
{{ hash.XxHash "Hello world" }} → c500b0c912b376d8
```

[xxHash](https://xxhash.com/) is a very fast non-cryptographic hash algorithm. Hugo uses [this Go implementation](https://github.com/cespare/xxhash).
