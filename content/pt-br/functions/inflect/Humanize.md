---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: inflect.Humanize
description: Returns the humanized version of the input with the first letter capitalized.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [humanize]
    returnType: string
    signatures: [inflect.Humanize INPUT]
aliases: [/functions/humanize]
---

```go-html-template
{{ humanize "my-first-post" }} → My first post
{{ humanize "myCamelPost" }} → My camel post
```

If the input is an integer or a string representation of an integer, humanize returns the number with the proper ordinal appended.

```go-html-template
{{ humanize "52" }} → 52nd
{{ humanize 103 }} → 103rd
```
