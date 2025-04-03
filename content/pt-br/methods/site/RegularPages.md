---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: RegularPages
description: Returns a collection of all regular pages.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Pages
    signatures: [SITE.RegularPages]
---

The `RegularPages` method on a `Site` object returns a collection of all [regular pages](g), in the [default sort order](g).

```go-html-template
{{ range .Site.RegularPages }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

{{% glossary-term "default sort order" %}}

[default sort order](g)

To change the sort order, use any of the `Pages` [sorting methods]. For example:

```go-html-template
{{ range .Site.RegularPages.ByTitle }}
  <h2><a href="{{ .RelPermalink }}">{{ .Title }}</a></h2>
{{ end }}
```

[sorting methods]: /methods/pages/
