---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: WordCount
description: Returns the number of words in the content of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [PAGE.WordCount]
---

```go-html-template
{{ .WordCount }} → 103
```

To round up to nearest multiple of 100, use the [`FuzzyWordCount`] method.

[`FuzzyWordCount`]: /methods/page/fuzzywordcount/
