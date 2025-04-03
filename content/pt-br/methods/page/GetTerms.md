---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: GetTerms
description: Returns a collection of term pages for terms defined on the given page in the given taxonomy, ordered according to the sequence in which they appear in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Pages
    signatures: [PAGE.GetTerms TAXONOMY]
---

Given this front matter:

{{< code-toggle file=content/books/les-miserables.md fm=true >}}
title = 'Les Misérables'
tags = ['historical','classic','fiction']
{{< /code-toggle >}}

This template code:

```go-html-template
{{ with .GetTerms "tags" }}
  <p>Tags</p>
  <ul>
    {{ range . }}
      <li><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

Is rendered to:

```html
<p>Tags</p>
<ul>
  <li><a href="/tags/historical/">historical</a></li>
  <li><a href="/tags/classic/">classic</a></li>
  <li><a href="/tags/fiction/">fiction</a></li>
</ul>
```
