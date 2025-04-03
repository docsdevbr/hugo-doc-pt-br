---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Draft
description: Reports whether the given page is a draft as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [PAGE.Draft]
---

By default, Hugo does not publish draft pages when you build your site. To include draft pages when you build your site, use the `--buildDrafts` command line flag.

{{< code-toggle file=content/posts/post-1.md fm=true >}}
title = 'Post 1'
draft = true
{{< /code-toggle >}}

```go-html-template
{{ .Draft }} → true
```
