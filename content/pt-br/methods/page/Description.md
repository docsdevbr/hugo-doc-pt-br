---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Description
description: Returns the description of the given page as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Description]
---

Conceptually different from a [content summary], a page description is typically used in metadata about the page.

{{< code-toggle file=content/recipes/sushi.md fm=true >}}
title = 'How to make spicy tuna hand rolls'
description = 'Instructions for making spicy tuna hand rolls.'
{{< /code-toggle >}}

```go-html-template {file="layouts/_default/baseof.html"}
<head>
  ...
  <meta name="description" content="{{ .Description }}">
  ...
</head>
```

[content summary]: /content-management/summaries/
