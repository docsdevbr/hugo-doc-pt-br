---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Slug
description: Returns the URL slug of the given page as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Slug]
---

{{< code-toggle file=content/recipes/spicy-tuna-hand-rolls.md fm=true >}}
title = 'How to make spicy tuna hand rolls'
slug = 'sushi'
{{< /code-toggle >}}

This page will be served from:

    https://example.org/recipes/sushi

To get the slug value within a template:

```go-html-template
{{ .Slug }} → sushi
```
