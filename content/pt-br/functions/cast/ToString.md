---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: cast.ToString
description: Converts a value to a string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [string]
    returnType: string
    signatures: [cast.ToString INPUT]
aliases: [/functions/string]
---

With a decimal (base 10) input:

```go-html-template
{{ string 11 }} → 11 (string)
{{ string "11" }} → 11 (string)

{{ string 11.1 }} → 11.1 (string)
{{ string "11.1" }} → 11.1 (string)

{{ string 11.9 }} → 11.9 (string)
{{ string "11.9" }} → 11.9 (string)
```

With a binary (base 2) input:

```go-html-template
{{ string 0b11 }} → 3 (string)
{{ string "0b11" }} → 0b11 (string)
```

With an octal (base 8) input (use either notation):

```go-html-template
{{ string 011 }} → 9 (string)
{{ string "011" }} → 011 (string)

{{ string 0o11 }} → 9 (string)
{{ string "0o11" }} → 0o11 (string)
```

With a hexadecimal (base 16) input:

```go-html-template
{{ string 0x11 }} → 17 (string)
{{ string "0x11" }} → 0x11 (string)
```
