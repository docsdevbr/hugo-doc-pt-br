---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.TrimSpace
description: Returns the given string, removing leading and trailing whitespace as defined by Unicode.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [strings.TrimSpace INPUT]
---

{{< new-in 0.136.3 />}}

Whitespace characters include `\t`, `\n`, `\v`, `\f`, `\r`, and characters in the [Unicode Space Separator] category.

[Unicode Space Separator]: https://www.compart.com/en/unicode/category/Zs

```go-html-template
{{ strings.TrimSpace "\n\r\t   foo   \n\r\t" }} → foo
```
