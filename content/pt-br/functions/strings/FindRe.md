---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.FindRE
description: Returns a slice of strings that match the regular expression.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [findRE]
    returnType: '[]string'
    signatures: ['strings.FindRE PATTERN INPUT [LIMIT]']
aliases: [/functions/findre]
---
By default, `findRE` finds all matches. You can limit the number of matches with an optional LIMIT argument.

{{% include "/_common/functions/regular-expressions.md" %}}

This example returns a slice of all second level headings (`h2` elements) within the rendered `.Content`:

```go-html-template
{{ findRE `(?s)<h2.*?>.*?</h2>` .Content }}
```

The `s` flag causes `.` to match `\n` as well, allowing us to find an `h2` element that contains newlines.

To limit the number of matches to one:

```go-html-template
{{ findRE `(?s)<h2.*?>.*?</h2>` .Content 1 }}
```

> [!note]
> You can write and test your regular expression using [regex101.com](https://regex101.com/). Be sure to select the Go flavor before you begin.
