---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Store
description: Returns a "scratch pad" to store and manipulate data, scoped to the current page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: maps.Scratch
    signatures: [PAGE.Store]
aliases: [/functions/store/,/extras/scratch/,/doc/scratch/,/functions/scratch]
---

Use the `Store` method on a `Page` object to create a [scratch pad](g) to store and manipulate data, scoped to the current page. To create a scratch pad with a different [scope](g), refer to the [scope](#scope) section below.

{{% include "_common/store-methods.md" %}}

{{% include "_common/scratch-pad-scope.md" %}}

## Determinate values

The `Store` method is often used to set scratch pad values within a shortcode, a partial template called by a shortcode, or by a Markdown render hook. In all three cases, the scratch pad values are indeterminate until Hugo renders the page content.

If you need to access a scratch pad value from a parent template, and the parent template has not yet rendered the page content, you can trigger content rendering by assigning the returned value to a [noop](g) variable:

```go-html-template
{{ $noop := .Content }}
{{ .Store.Get "mykey" }}
```

You can also trigger content rendering with the `ContentWithoutSummary`, `FuzzyWordCount`, `Len`, `Plain`, `PlainWords`, `ReadingTime`, `Summary`, `Truncated`, and `WordCount` methods. For example:

```go-html-template
{{ $noop := .WordCount }}
{{ .Store.Get "mykey" }}
```
