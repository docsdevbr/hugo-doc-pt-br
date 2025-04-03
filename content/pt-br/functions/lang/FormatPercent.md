---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: lang.FormatPercent
description: Returns a percentage representation of a number with the given precision for the current language and region.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [lang.FormatPercent PRECISION NUMBER]
---

```go-html-template
{{ 512.5032 | lang.FormatPercent 2 }} → 512.50%
```

{{% include "/_common/functions/locales.md" %}}
