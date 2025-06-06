---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: compare.Conditional
description: Returns one of two arguments depending on the value of the control argument.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [cond]
    returnType: any
    signatures: [compare.Conditional CONTROL ARG1 ARG2]
aliases: [/functions/cond]
---

If CONTROL is truthy the function returns ARG1, otherwise it returns ARG2.

```go-html-template
{{ $qty := 42 }}
{{ cond (le $qty 3) "few" "many" }} → many
```

Unlike [ternary operators] in other languages, the `compare.Conditional` function does not perform [short-circuit evaluation]. It evaluates both ARG1 and ARG2 regardless of the CONTROL value.

[short-circuit evaluation]: https://en.wikipedia.org/wiki/Short-circuit_evaluation
[ternary operators]: https://en.wikipedia.org/wiki/Ternary_conditional_operator

Due to the absence of short-circuit evaluation, these examples throw an error:

```go-html-template
{{ cond true "true" (div 1 0) }}
{{ cond false (div 1 0) "false" }}
```
