---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Truncate
description: Returns the given string, truncating it to a maximum length without cutting words or leaving unclosed HTML tags.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [truncate]
    returnType: template.HTML
    signatures: ['strings.Truncate SIZE [ELLIPSIS] INPUT']
aliases: [/functions/truncate]
---

Since Go templates are HTML-aware, `truncate` will intelligently handle normal strings vs HTML strings:

```go-html-template
{{ "<em>Keep my HTML</em>" | safeHTML | truncate 10 }} → <em>Keep my …</em>
```

> [!note]
> If you have a raw string that contains HTML tags you want to remain treated as HTML, you will need to convert the string to HTML using the [`safeHTML`]function before sending the value to `truncate`. Otherwise, the HTML tags will be escaped when passed through the `truncate` function.

[`safeHTML`]: /functions/safe/html/
