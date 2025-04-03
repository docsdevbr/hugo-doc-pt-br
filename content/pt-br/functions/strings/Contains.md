---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Contains
description: Reports whether the given string contains the given substring.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [strings.Contains STRING SUBSTRING]
aliases: [/functions/strings.contains]
---

```go-html-template
{{ strings.Contains "Hugo" "go" }} → true
```

The check is case sensitive:

```go-html-template
{{ strings.Contains "Hugo" "Go" }} → false
```
