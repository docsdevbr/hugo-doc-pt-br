---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: LinkTitle
description: Returns the link title of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.LinkTitle]
---

The `LinkTitle` method returns the `linkTitle` field as defined in front matter, falling back to the value returned by the [`Title`] method.

[`Title`]: /methods/page/title/

{{< code-toggle file=content/articles/healthy-desserts.md fm=true >}}
title = 'Seventeen delightful recipes for healthy desserts'
linkTitle = 'Dessert recipes'
{{< /code-toggle >}}

```go-html-template
{{ .LinkTitle }} → Dessert recipes
```

As demonstrated above, defining a link title in front matter is advantageous when the page title is long. Use it when generating anchor elements in your templates:

```go-html-template
<a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a>
```
