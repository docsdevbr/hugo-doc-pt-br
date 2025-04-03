---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: resources.Minify
description: Minifies the given resource.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [minify]
    returnType: resource.Resource
    signatures: [resources.Minify RESOURCE]
---

```go-html-template
{{ $css := resources.Get "css/main.css" }}
{{ $style := $css | minify }}
```

Any CSS, JS, JSON, HTML, SVG, or XML resource can be minified using resources.Minify which takes for argument the resource object.
