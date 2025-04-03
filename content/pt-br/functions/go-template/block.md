---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: block
description: Defines a template and executes it in place.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType:
    signatures: [block NAME CONTEXT]
---

A block is shorthand for defining a template:

```go-html-template
{{ define "name" }} T1 {{ end }}
```

and then executing it in place:

```go-html-template
{{ template "name" pipeline }}
```
The typical use is to define a set of root templates that are then customized by redefining the block templates within.

```go-html-template {file="layouts/_default/baseof.html"}
<body>
  <main>
    {{ block "main" . }}
      {{ print "default value if 'main' template is empty" }}
    {{ end }}
  </main>
</body>
```

```go-html-template {file="layouts/_default/single.html"}
{{ define "main" }}
  <h1>{{ .Title }}</h1>
  {{ .Content }}
{{ end }}
```

```go-html-template {file="layouts/_default/list.html"}
{{ define "main" }}
  <h1>{{ .Title }}</h1>
  {{ .Content }}
  {{ range .Pages }}
    <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
  {{ end }}
{{ end }}
```

{{% include "/_common/functions/go-template/text-template.md" %}}
