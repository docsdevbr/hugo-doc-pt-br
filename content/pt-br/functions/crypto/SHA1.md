---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: crypto.SHA1
description: Hashes the given input and returns its SHA1 checksum encoded to a hexadecimal string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [sha1]
    returnType: string
    signatures: [crypto.SHA1 INPUT]
aliases: [/functions/sha,/functions/sha1]
---

```go-html-template
{{ sha1 "Hello world" }} → 7b502c3a1f48c8609ae212cdfb639dee39673f5e
```
