---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: urls.URLize
description: Returns the given string, sanitized for usage in a URL.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [urlize]
    returnType: string
    signatures: [urls.URLize INPUT]
aliases: [/functions/urlize]
---

{{% include "/_common/functions/urls/anchorize-vs-urlize.md" %}}

## Example

Use the `urlize` function to create a link to a [term page](g).

Consider this site configuration:

{{< code-toggle file=hugo >}}
[taxonomies]
author = 'authors'
{{< /code-toggle >}}

And this front matter:

{{< code-toggle file=content/books/les-miserables.md fm=true >}}
title = 'Les Misérables'
authors = ['Victor Hugo']
{{< /code-toggle >}}

The published site will have this structure:

```text
public/
├── authors/
│   ├── victor-hugo/
│   │   └── index.html
│   └── index.html
├── books/
│   ├── les-miserables/
│   │   └── index.html
│   └── index.html
└── index.html
```

To create a link to the term page:

```go-html-template
{{ $taxonomy := "authors" }}
{{ $term := "Victor Hugo" }}
{{ with index .Site.Taxonomies $taxonomy (urlize $term) }}
  <a href="{{ .Page.RelPermalink }}">{{ .Page.LinkTitle }}</a>
{{ end }}
```

To generate a list of term pages associated with a given content page, use the [`GetTerms`] method on a `Page` object.

[`GetTerms`]: /methods/page/getterms/
