---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Param
description: Returns the site parameter with the given key.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: any
    signatures: [SITE.Param KEY]
---

The `Param` method on a `Site` object is a convenience method to return the value of a user-defined parameter in the site configuration.

{{< code-toggle file=hugo >}}
[params]
display_toc = true
{{< /code-toggle >}}

```go-html-template
{{ .Site.Param "display_toc" }} → true
```

The above is equivalent to either of these:

```go-html-template
{{ .Site.Params.display_toc }}
{{ index .Site.Params "display_toc" }}
```
