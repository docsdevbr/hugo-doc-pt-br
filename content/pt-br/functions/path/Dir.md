---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: path.Dir
description: Replaces path separators with slashes (/) and returns all but the last element of the given path.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [path.Dir PATH]
aliases: [/functions/path.dir]
---

```go-html-template
{{ path.Dir "a/news.html" }} → a
{{ path.Dir "news.html" }} → .
{{ path.Dir "a/b/c" }} → a/b
{{ path.Dir "/a/b/c" }} → /a/b
{{ path.Dir "/a/b/c/" }} → /a/b/c
{{ path.Dir "" }} → .
```
