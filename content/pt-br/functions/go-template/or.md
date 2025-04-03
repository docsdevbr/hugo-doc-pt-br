---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: or
description: Returns the first truthy argument. If all arguments are falsy, returns the last argument.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: any
    signatures: [or VALUE...]
---

{{% include "/_common/functions/truthy-falsy.md" %}}

```go-html-template
{{ or 0 1 2 }} → 1
{{ or false "a" 1 }} → a
{{ or 0 true "a" }} → true

{{ or false "" 0 }} → 0
{{ or 0 "" false }} → false
```

{{% include "/_common/functions/go-template/text-template.md" %}}
