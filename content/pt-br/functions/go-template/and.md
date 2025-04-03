---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: and
description: Returns the first falsy argument. If all arguments are truthy, returns the last argument.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: any
    signatures: [and VALUE...]
---

{{% include "/_common/functions/truthy-falsy.md" %}}

```go-html-template
{{ and 1 0 "" }} → 0 (int)
{{ and 1 false 0 }} → false (bool)

{{ and 1 2 3 }} → 3 (int)
{{ and "a" "b" "c" }} → c (string)
{{ and "a" 1 true }} → true (bool)
```
