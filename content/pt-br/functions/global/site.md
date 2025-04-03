---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: site
description: Provides global access to the current Site object.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: 
    signatures: [site]
aliases: [/functions/site]
---

Use the `site` function to return the `Site` object regardless of current context.

```go-html-template
{{ site.Params.foo }}
```

When the `Site` object is in context you can use the `Site` property:

```go-html-template
<!-- current context -->
{{ .Site.Params.foo }}
<!-- template context -->
{{ $.Site.Params.foo }}
```

> [!note]
> To simplify your templates, use the global `site` function regardless of whether the `Site` object is in context.
