---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Alphabetical
description: Returns an ordered taxonomy, sorted alphabetically by term.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.OrderedTaxonomy
    signatures: [TAXONOMY.Alphabetical]
---

The `Alphabetical` method on a `Taxonomy` object returns an [ordered taxonomy](g), sorted alphabetically by [term](g).

While a `Taxonomy` object is a [map](g), an ordered taxonomy is a [slice](g), where each element is an object that contains the term and a slice of its [weighted pages](g).

{{% include "/_common/methods/taxonomy/get-a-taxonomy-object.md" %}}

## Get the ordered taxonomy

Now that we have captured the “genres” Taxonomy object, let's get the ordered taxonomy sorted alphabetically by term:

```go-html-template
{{ $taxonomyObject.Alphabetical }}
```

To reverse the sort order:

```go-html-template
{{ $taxonomyObject.Alphabetical.Reverse }}
```

To inspect the data structure:

```go-html-template
<pre>{{ debug.Dump $taxonomyObject.Alphabetical }}</pre>
```

{{% include "/_common/methods/taxonomy/ordered-taxonomy-element-methods.md" %}}

## Example

With this template:

```go-html-template
{{ range $taxonomyObject.Alphabetical }}
  <h2><a href="{{ .Page.RelPermalink }}">{{ .Page.LinkTitle }}</a> ({{ .Count }})</h2>
  <ul>
    {{ range .Pages.ByTitle }}
      <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

Hugo renders:

```html
<h2><a href="/genres/romance/">romance</a> (2)</h2>
<ul>
  <li><a href="/books/jamaica-inn/">Jamaica inn</a></li>
  <li><a href="/books/pride-and-prejudice/">Pride and prejudice</a></li>
</ul>
<h2><a href="/genres/suspense/">suspense</a> (3)</h2>
<ul>
  <li><a href="/books/and-then-there-were-none/">And then there were none</a></li>
  <li><a href="/books/death-on-the-nile/">Death on the nile</a></li>
  <li><a href="/books/jamaica-inn/">Jamaica inn</a></li>
</ul>
```
