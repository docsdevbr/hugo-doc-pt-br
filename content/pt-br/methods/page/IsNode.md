---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: IsNode
description: Reports whether the given page is a node.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [PAGE.IsNode]
---

The `IsNode` method on a `Page` object returns `true` if the [page kind](g) is `home`, `section`, `taxonomy`, or `term`.

It returns `false` is the page kind is `page`.

```text
content/
├── books/
│   ├── book-1/
│   │   └── index.md    <-- kind = page, node = false
│   ├── book-2.md       <-- kind = page, node = false
│   └── _index.md       <-- kind = section, node = true
├── tags/
│   ├── fiction/
│   │   └── _index.md   <-- kind = term, node = true
│   └── _index.md       <-- kind = taxonomy, node = true
└── _index.md           <-- kind = home, node = true
```

```go-html-template
{{ .IsNode }}
```
