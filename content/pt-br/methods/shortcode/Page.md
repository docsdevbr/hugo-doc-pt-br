---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Page
description: Returns the Page object from which the shortcode was called.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: hugolib.pageForShortcode
    signatures: [SHORTCODE.Page]
---

With this content:

{{< code-toggle file=content/books/les-miserables.md fm=true >}}
title = 'Les Misérables'
author = 'Victor Hugo'
publication_year = 1862
isbn = '978-0451419439'
{{< /code-toggle >}}

Calling this shortcode:

```text
{{</* book-details */>}}
```

We can access the front matter values using the `Page` method:

```go-html-template {file="layouts/shortcodes/book-details.html"}
<ul>
  <li>Title: {{ .Page.Title }}</li>
  <li>Author: {{ .Page.Params.author }}</li>
  <li>Published: {{ .Page.Params.publication_year }}</li>
  <li>ISBN: {{ .Page.Params.isbn }}</li>
</ul>
```
