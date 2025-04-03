---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: cast.ToFloat
description: Converts a value to a decimal floating-point number (base 10).
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [float]
    returnType: float64
    signatures: [cast.ToFloat INPUT]
aliases: [/functions/float]
---

With a decimal (base 10) input:

```go-html-template
{{ float 11 }} → 11 (float64)
{{ float "11" }} → 11 (float64)

{{ float 11.1 }} → 11.1 (float64)
{{ float "11.1" }} → 11.1 (float64)

{{ float 11.9 }} → 11.9 (float64)
{{ float "11.9" }} → 11.9 (float64)
```

With a binary (base 2) input:

```go-html-template
{{ float 0b11 }} → 3 (float64)
```

With an octal (base 8) input (use either notation):

```go-html-template
{{ float 011 }} → 9 (float64)
{{ float "011" }} → 11 (float64)

{{ float 0o11 }} → 9 (float64)
```

With a hexadecimal (base 16) input:

```go-html-template
{{ float 0x11 }} → 17 (float64)
```
