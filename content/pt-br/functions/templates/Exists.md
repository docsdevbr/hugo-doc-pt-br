---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: templates.Exists
description: Reports whether a template file exists under the given path relative to the layouts directory.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: bool
    signatures: [templates.Exists PATH]
aliases: [/functions/templates.exists]
---

A template file is any file within the `layouts` directory of either the project or any of its theme components.

Use the `templates.Exists` function with dynamic template paths:

```go-html-template
{{ $partialPath := printf "headers/%s.html" .Type }}
{{ if templates.Exists ( printf "partials/%s" $partialPath ) }}
  {{ partial $partialPath . }}
{{ else }}
  {{ partial "headers/default.html" . }}
{{ end }}
```

In the example above, if a "headers" partial does not exist for the given content type, Hugo falls back to a default template.
