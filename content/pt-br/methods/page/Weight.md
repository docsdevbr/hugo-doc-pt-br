---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Weight
description: Returns the weight of the given page as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [PAGE.Weight]
---

The `Weight` method on a `Page` object returns the [weight](g) of the given page as defined in front matter.

{{< code-toggle file=content/recipes/sushi.md fm=true >}}
title = 'How to make spicy tuna hand rolls'
weight = 42
{{< /code-toggle >}}

Page weight controls the position of a page within a collection that is sorted by weight. Assign weights using non-zero integers. Lighter items float to the top, while heavier items sink to the bottom. Unweighted or zero-weighted elements are placed at the end of the collection.

Although rarely used within a template, you can access the value with:

```go-html-template
{{ .Weight }} → 42
```
