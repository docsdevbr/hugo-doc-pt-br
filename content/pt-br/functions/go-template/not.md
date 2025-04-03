---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: not
description: Returns the boolean negation of its single argument.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [not VALUE]
---

Unlike the `and` and `or` operators, the `not` operator always returns a boolean value.

```go-html-template
{{ not true }} → false
{{ not false }} → true

{{ not 1 }} → false
{{ not 0 }} → true

{{ not "x" }} → false
{{ not "" }} → true
```

Use the `not` operator, twice in succession, to cast any value to a boolean value. For example:

```go-html-template
{{ 42 | not | not }} → true
{{ "" | not | not }} → false
```

{{% include "/_common/functions/go-template/text-template.md" %}}
