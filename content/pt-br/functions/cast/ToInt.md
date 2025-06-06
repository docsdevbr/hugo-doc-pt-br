---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: cast.ToInt
description: Converts a value to a decimal integer (base 10).
keywords: []
params:
  functions_and_methods:
    aliases: [int]
    returnType: int
    signatures: [cast.ToInt INPUT]
aliases: [/functions/int]
---

With a decimal (base 10) input:

```go-html-template
{{ int 11 }} → 11 (int)
{{ int "11" }} → 11 (int)

{{ int 11.1 }} → 11 (int)
{{ int 11.9 }} → 11 (int)
```

With a binary (base 2) input:

```go-html-template
{{ int 0b11 }} → 3 (int)
{{ int "0b11" }} → 3 (int)
```

With an octal (base 8) input (use either notation):

```go-html-template
{{ int 011 }} → 9 (int)
{{ int "011" }} → 9 (int)

{{ int 0o11 }} → 9 (int)
{{ int "0o11" }} → 9 (int)
```

With a hexadecimal (base 16) input:

```go-html-template
{{ int 0x11 }} → 17 (int)
{{ int "0x11" }} → 17 (int)
```

> [!note]
> Values with a leading zero are octal (base 8). When casting a string representation of a decimal (base 10) number, remove leading zeros:

`{{ strings.TrimLeft "0" "0011" | int }} → 11`
