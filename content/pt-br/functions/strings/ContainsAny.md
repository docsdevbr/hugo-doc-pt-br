---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.ContainsAny
description: Reports whether the given string contains any character within the given set.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [strings.ContainsAny STRING SET]
aliases: [/functions/strings.containsany]
---

```go-html-template
{{ strings.ContainsAny "Hugo" "gm" }} → true
```

The check is case sensitive:

```go-html-template
{{ strings.ContainsAny "Hugo" "Gm" }} → false
```
