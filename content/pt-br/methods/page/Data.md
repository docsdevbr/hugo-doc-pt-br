---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Data
description: Returns a unique data object for each page kind.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Data
    signatures: [PAGE.Data]
---

The `Data` method on a `Page` object returns a unique data object for each [page kind](g).

> [!note]
> The `Data` method is only useful within [taxonomy](g) and [term](g) templates.
>
> Themes that are not actively maintained may still use `.Data.Pages` in list templates. Although that syntax remains functional, use one of these methods instead: [`Pages`], [`RegularPages`], or [`RegularPagesRecursive`]

The examples that follow are based on this site configuration:

{{< code-toggle file=hugo >}}
[taxonomies]
genre = 'genres'
author = 'authors'
{{< /code-toggle >}}

And this content structure:

```text
content/
├── books/
│   ├── and-then-there-were-none.md --> genres: suspense
│   ├── death-on-the-nile.md        --> genres: suspense
│   └── jamaica-inn.md              --> genres: suspense, romance
│   └── pride-and-prejudice.md      --> genres: romance
└── _index.md
```

## In a taxonomy template

Use these methods on the `Data` object within a taxonomy template.

Singular
: (`string`) Returns the singular name of the taxonomy.

```go-html-template
{{ .Data.Singular }} → genre
```

Plural
: (`string`) Returns the plural name of the taxonomy.

```go-html-template
{{ .Data.Plural }} → genres
```

Terms
: (`page.Taxonomy`) Returns the `Taxonomy` object, consisting of a map of terms and the [weighted pages](g) associated with each term.

```go-html-template
{{ $taxonomyObject := .Data.Terms }} 
```

> [!note]
> Once you have captured the `Taxonomy` object, use any of the [taxonomy methods] to sort, count, or capture a subset of its weighted pages.

Learn more about [taxonomy templates].

## In a term template

Use these methods on the `Data` object within a term template.

Singular
: (`string`) Returns the singular name of the taxonomy.

```go-html-template
{{ .Data.Singular }} → genre
```

Plural
: (`string`) Returns the plural name of the taxonomy.

```go-html-template
{{ .Data.Plural }} → genres
```

Term
: (`string`) Returns the name of the term.

```go-html-template
{{ .Data.Term }} → suspense
```

Learn more about [term templates].

[`Pages`]: /methods/page/pages/
[`RegularPages`]: /methods/page/regularpages/
[`RegularPagesRecursive`]: /methods/page/regularpagesrecursive/
[taxonomy methods]: /methods/taxonomy/
[taxonomy templates]: /templates/types/#taxonomy
[term templates]: /templates/types/#term
