---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.HTMLEscape
description: Returns the given string, escaping special characters by replacing them with HTML entities.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [htmlEscape]
    returnType: string
    signatures: [transform.HTMLEscape INPUT]
aliases: [/functions/htmlescape]
---

The `transform.HTMLEscape` function escapes five special characters by replacing them with [HTML entities]:

- `&` → `&amp;`
- `<` → `&lt;`
- `>` → `&gt;`
- `'` → `&#39;`
- `"` → `&#34;`

For example:

```go-html-template
{{ htmlEscape "Lilo & Stitch" }} → Lilo &amp; Stitch
{{ htmlEscape "7 > 6" }} → 7 &gt; 6
```

[html entities]: https://developer.mozilla.org/en-US/docs/Glossary/Entity
