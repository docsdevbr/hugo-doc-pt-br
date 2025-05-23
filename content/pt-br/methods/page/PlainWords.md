---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: PlainWords
description: Calls the Plain method, splits the result into a slice of words, and returns the slice.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: '[]string'
    signatures: [PAGE.PlainWords]
---

The `PlainWords` method on a `Page` object calls the [`Plain`] method, then uses Go's [`strings.Fields`] function to split the result into words.

> [!note]
> `Fields` splits the string `s` around each instance of one or more consecutive whitespace characters, as defined by [`unicode.IsSpace`], returning a slice of substrings of `s` or an empty slice if `s` contains only whitespace.

As a result, elements within the slice may contain leading or trailing punctuation.

```go-html-template
{{ .PlainWords }}
```

To determine the approximate number of unique words on a page:

```go-html-template
{{ .PlainWords | uniq }} → 42
```

[`Plain`]: /methods/page/plain/
[`strings.Fields`]: https://pkg.go.dev/strings#Fields
[`unicode.IsSpace`]: https://pkg.go.dev/unicode#IsSpace
