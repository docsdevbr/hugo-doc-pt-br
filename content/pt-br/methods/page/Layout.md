---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Layout
description: Returns the layout for the given page as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Layout]
---

Specify the `layout` field in front matter to target a particular template. See&nbsp;[details].

[details]: /templates/lookup-order/#target-a-template

{{< code-toggle file=content/contact.md fm=true >}}
title = 'Contact'
layout = 'contact'
{{< /code-toggle >}}

Hugo will render the page using contact.html.

```text
layouts/
└── _default/
    ├── baseof.html
    ├── contact.html
    ├── home.html
    ├── list.html
    └── single.html
```

Although rarely used within a template, you can access the value with:

```go-html-template
{{ .Layout }}
```

The `Layout` method returns an empty string if the `layout` field in front matter is not defined.
