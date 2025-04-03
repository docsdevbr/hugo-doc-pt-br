---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: ByLinkTitle
description: Returns the given page collection sorted by link title in ascending order, falling back to title if link title is not defined.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Pages
    signatures: [PAGES.ByLinkTitle]
---

```go-html-template
{{ range .Pages.ByLinkTitle }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

To sort in descending order:

```go-html-template
{{ range .Pages.ByLinkTitle.Reverse }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```
