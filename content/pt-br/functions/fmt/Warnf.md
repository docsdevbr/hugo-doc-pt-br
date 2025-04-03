---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: fmt.Warnf
description: Log a WARNING from a template.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [warnf]
    returnType: string
    signatures: ['fmt.Warnf FORMAT [INPUT]']
aliases: [/functions/warnf]
---

{{% include "/_common/functions/fmt/format-string.md" %}}

The `warnf` function evaluates the format string, then prints the result to the WARNING log. Hugo prints each unique message once to avoid flooding the log with duplicate warnings.

```go-html-template
{{ warnf "The %q shortcode was unable to find %s. See %s" .Name $file .Position }}
```

Use the [`warnidf`] function to allow optional suppression of specific warnings.

To prevent suppression of duplicate messages when using `warnf` for debugging, make each message unique with the [`math.Counter`] function. For example:

```go-html-template
{{ range site.RegularPages }}
  {{ .Section | warnf "%#[2]v [%[1]d]" math.Counter }}
{{ end }}
```

[`math.Counter`]: /functions/math/counter/

[`warnidf`]: /functions/fmt/warnidf/
