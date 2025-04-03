---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: hugo.BuildDate
description: Returns the compile date of the Hugo binary.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [hugo.BuildDate]
---

The `hugo.BuildDate` function returns the compile date of the Hugo binary, formatted per [RFC 3339].

[RFC 3339]: https://datatracker.ietf.org/doc/html/rfc3339

```go-html-template
{{ hugo.BuildDate }} → 2023-11-01T17:57:00Z
```
