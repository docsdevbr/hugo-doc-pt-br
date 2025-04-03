---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Home
description: Returns the home Page object for the given site.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Page
    signatures: [SITE.Home]
---

This method is useful for obtaining a link to the home page.

Site configuration:

{{< code-toggle file=hugo >}}
baseURL = 'https://example.org/docs/'
{{< /code-toggle >}}

Template:

```go-html-template
{{ .Site.Home.Permalink }} → https://example.org/docs/ 
{{ .Site.Home.RelPermalink }} → /docs/
```
