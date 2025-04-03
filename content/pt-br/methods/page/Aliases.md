---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Aliases
description: Returns the URL aliases as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: '[]string'
    signatures: [PAGE.Aliases]
---

The `Aliases` method on a `Page` object returns the URL [aliases] as defined in front matter.

For example:

{{< code-toggle file=content/about.md fm=true >}}
title = 'About'
aliases = ['/old-url','/really-old-url']
{{< /code-toggle >}}

To list the aliases:

```go-html-template
{{ range .Aliases }}
  {{ . }}
{{ end }}
```

[aliases]: /content-management/urls/#aliases
