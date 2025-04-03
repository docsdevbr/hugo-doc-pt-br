---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: lang.FormatNumberCustom
description: Returns a numeric representation of a number with the given precision using negative, decimal, and grouping options.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: ['lang.FormatNumberCustom PRECISION NUMBER [OPTIONS...]']
aliases: ['/functions/numfmt/']
---

This function formats a number with the given precision. The first options parameter is a space-delimited string of characters to represent negativity, the decimal point, and grouping. The default value is `- . ,`. The second options parameter defines an alternative delimiting character.

Note that numbers are rounded up at 5 or greater. So, with precision set to 0, 1.5 becomes 2, and 1.4 becomes&nbsp;1.

For a simpler function that adapts to the current language, see [`lang.FormatNumber`].

```go-html-template
{{ lang.FormatNumberCustom 2 12345.6789 }} → 12,345.68
{{ lang.FormatNumberCustom 2 12345.6789 "- , ." }} → 12.345,68
{{ lang.FormatNumberCustom 6 -12345.6789 "- ." }} → -12345.678900
{{ lang.FormatNumberCustom 0 -12345.6789 "- . ," }} → -12,346
{{ lang.FormatNumberCustom 0 -12345.6789 "-|.| " "|" }} → -12 346
```

{{% include "/_common/functions/locales.md" %}}

[`lang.FormatNumber`]: /functions/lang/formatnumber/
