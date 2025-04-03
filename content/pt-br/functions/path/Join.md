---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: path.Join
description: Replaces path separators with slashes (`/`), joins the given path elements into a single path, and returns the shortest path name equivalent to the result.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [path.Join ELEMENT...]
aliases: [/functions/path.join]
---

See Go's [`path.Join`] and [`path.Clean`] documentation for details.

[`path.Clean`]: https://pkg.go.dev/path#Clean
[`path.Join`]: https://pkg.go.dev/path#Join

```go-html-template
{{ path.Join "partial" "news.html" }} → partial/news.html
{{ path.Join "partial/" "news.html" }} → partial/news.html
{{ path.Join "foo/bar" "baz" }} → foo/bar/baz
{{ path.Join "foo" "bar" "baz" }} → foo/bar/baz
{{ path.Join "foo" "" "baz" }} → foo/baz
{{ path.Join "foo" "." "baz" }} → foo/baz
{{ path.Join "foo" ".." "baz" }} → baz
{{ path.Join "/.." "foo" ".." "baz" }} → baz
```
