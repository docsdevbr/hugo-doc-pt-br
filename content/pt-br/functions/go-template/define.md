---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: define
description: Defines a template.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType:
    signatures: [define NAME]
---

Use with the [`block`] statement:

```go-html-template
{{ block "main" . }}
  {{ print "default value if 'main' template is empty" }}
{{ end }}

{{ define "main" }}
  <h1>{{ .Title }}</h1>
  {{ .Content }}
{{ end }}
```

Use with the [`partial`] function:

```go-html-template
{{ partial "inline/foo.html" (dict "answer" 42) }}

{{ define "partials/inline/foo.html" }}
  {{ printf "The answer is %v." .answer }}
{{ end }}
```

Use with the [`template`] function:

```go-html-template
{{ template "foo" (dict "answer" 42) }}

{{ define "foo" }}
  {{ printf "The answer is %v." .answer }}
{{ end }}
```

[`block`]: /functions/go-template/block/
[`template`]: /functions/go-template/block/
[`partial`]: /functions/partials/include/

{{% include "/_common/functions/go-template/text-template.md" %}}
