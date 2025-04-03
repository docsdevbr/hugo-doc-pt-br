---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: fmt.Printf
description: Formats a string using the standard `fmt.Sprintf` function.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [printf]
    returnType: string
    signatures: ['fmt.Printf FORMAT [INPUT]']
aliases: [/functions/printf]
---

{{% include "/_common/functions/fmt/format-string.md" %}}

```go-html-template
{{ $var := "world" }}
{{ printf "Hello %s." $var }} → Hello world.
```

```go-html-template
{{ $pi := 3.14159265 }}
{{ printf "Pi is approximately %.2f." $pi }} → 3.14
```

Use the `printf` function with the `safeHTMLAttr` function:

```go-html-template
{{ $desc := "Eat at Joe's" }}
<meta name="description" {{ printf "content=%q" $desc | safeHTMLAttr }}>
```

Hugo renders this to:

```html
<meta name="description" content="Eat at Joe's">
```
