---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.TrimRight
description: Returns the given string, removing trailing characters specified in the cutset.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [strings.TrimRight CUTSET STRING]
aliases: [/functions/strings.trimright]
---

```go-html-template
{{ strings.TrimRight "a" "abba" }} → abb
```

The `strings.TrimRight` function converts the arguments to strings if possible:

```go-html-template
{{ strings.TrimRight 54 12345 }} → 123 (string)
{{ strings.TrimRight "eu" true }} → tr
```
