---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: debug.Dump
description: Returns an object dump as a string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [debug.Dump VALUE]
---

```go-html-template
<pre>{{ debug.Dump site.Data.books }}</pre>
```

```json
[
  {
    "author": "Victor Hugo",
    "rating": 4,
    "title": "The Hunchback of Notre Dame"
  },
  {
    "author": "Victor Hugo",
    "rating": 5,
    "title": "Les Misérables"
  }
]
```

> [!note]
> Output from this function may change from one release to the next. Use for debugging only.
