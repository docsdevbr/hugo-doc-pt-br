---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.HTMLUnescape
description: Returns the given string, replacing each HTML entity with its corresponding character.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [htmlUnescape]
    returnType: string
    signatures: [transform.HTMLUnescape INPUT]
aliases: [/functions/htmlunescape]
---

The `transform.HTMLUnescape` function replaces [HTML entities] with their corresponding characters.

```go-html-template
{{ htmlUnescape "Lilo &amp; Stitch" }} → Lilo & Stitch
{{ htmlUnescape "7 &gt; 6" }} → 7 > 6
```

In most contexts Go's [html/template] package will escape special characters. To bypass this behavior, pass the unescaped string through the [`safeHTML`] function.

```go-html-template
{{ htmlUnescape "Lilo &amp; Stitch" | safeHTML }}
```

[`safehtml`]: /functions/safe/html/
[html entities]: https://developer.mozilla.org/en-us/docs/glossary/entity
[html/template]: https://pkg.go.dev/html/template
