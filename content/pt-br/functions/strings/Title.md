---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Title
description: Returns the given string, converting it to title case.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [title]
    returnType: string
    signatures: [strings.Title STRING]
aliases: [/functions/title]
---

```go-html-template
{{ title "table of contents (TOC)" }} → Table of Contents (TOC)
```

By default, Hugo follows the capitalization rules published in the [Associated Press Stylebook]. Change your [site configuration] if you would prefer to:

- Follow the capitalization rules published in the [Chicago Manual of Style]
- Capitalize the first letter of every word
- Capitalize the first letter of the first word
- Disable the effects of the `title` function

The last option is useful if your theme uses the `title` function, and you would prefer to manually capitalize strings as needed.

[Associated Press Stylebook]: https://www.apstylebook.com/
[Chicago Manual of Style]: https://www.chicagomanualofstyle.org/home.html
[site configuration]: /configuration/all/#title-case-style
