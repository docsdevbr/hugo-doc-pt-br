---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: IsHome
description: Reports whether the given page is the home page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [PAGE.IsHome]
---

The `IsHome` method on a `Page` object returns `true` if the [page kind](g) is `home`.

```text
content/
├── books/
│   ├── book-1/
│   │   └── index.md  <-- kind = page
│   ├── book-2.md     <-- kind = page
│   └── _index.md     <-- kind = section
└── _index.md         <-- kind = home
```

```go-html-template
{{ .IsHome }}
```
