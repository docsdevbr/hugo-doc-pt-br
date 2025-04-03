---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: ByExpiryDate
description: Returns the given page collection sorted by expiration date in ascending order.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Pages
    signatures: [PAGES.ByExpiryDate]
---

When sorting by expiration date, the value is determined by your [site configuration], defaulting to the `expiryDate` field in front matter.

[site configuration]: /configuration/front-matter/#dates

```go-html-template
{{ range .Pages.ByExpiryDate }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

To sort in descending order:

```go-html-template
{{ range .Pages.ByExpiryDate.Reverse }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```
