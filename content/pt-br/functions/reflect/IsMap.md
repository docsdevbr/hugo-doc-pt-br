---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: reflect.IsMap
description: Reports whether the given value is a map.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [reflect.IsMap INPUT]
aliases: [/functions/reflect.ismap]
---

```go-html-template
{{ reflect.IsMap (dict "key" "value") }} → true
{{ reflect.IsMap "yo" }} → false
```
