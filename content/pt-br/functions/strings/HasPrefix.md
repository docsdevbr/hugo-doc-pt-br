---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.HasPrefix
description: Reports whether the given string begins with the given prefix.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [hasPrefix]
    returnType: bool
    signatures: [strings.HasPrefix STRING PREFIX]
aliases: [/functions/hasprefix,/functions/strings.hasprefix]
---

```go-html-template
{{ hasPrefix "Hugo" "Hu" }} → true
```
