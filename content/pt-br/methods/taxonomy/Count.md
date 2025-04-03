---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Count
description: Returns the number of number of weighted pages to which the given term has been assigned.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: int
    signatures: [TAXONOMY.Count TERM]
---

The `Count` method on a `Taxonomy` object returns the number of number of [weighted pages](g) to which the given [term](g) has been assigned.

{{% include "/_common/methods/taxonomy/get-a-taxonomy-object.md" %}}

## Count the weighted pages

Now that we have captured the "genres" `Taxonomy` object, let's count the number of weighted pages to which the "suspense" term has been assigned:

```go-html-template
{{ $taxonomyObject.Count "suspense" }} → 3
```
