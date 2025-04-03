---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: fmt.Errorf
description: Log an ERROR from a template.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [errorf]
    returnType: string
    signatures: ['fmt.Errorf FORMAT [INPUT]']
aliases: [/functions/errorf]
---

{{% include "/_common/functions/fmt/format-string.md" %}}

The `errorf` function evaluates the format string, then prints the result to the ERROR log and fails the build.

```go-html-template
{{ errorf "The %q shortcode requires a src argument. See %s" .Name .Position }}
```

Use the [`erroridf`] function to allow optional suppression of specific errors.

[`erroridf`]: /functions/fmt/erroridf/
