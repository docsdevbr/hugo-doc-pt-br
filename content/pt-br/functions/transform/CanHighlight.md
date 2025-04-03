---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.CanHighlight
description: Reports whether the given code language is supported by the Chroma highlighter.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [transform.CanHighlight LANGUAGE]
---

```go-html-template
{{ transform.CanHighlight "go" }} → true
{{ transform.CanHighlight "klingon" }} → false
```
