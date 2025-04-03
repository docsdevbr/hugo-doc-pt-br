---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: continue
description: Used with the range statement, stops the innermost iteration and continues to the next iteration.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType:
    signatures: [continue]
---

This template code:

```go-html-template
{{ $s := slice "foo" "bar" "baz" }}
{{ range $s }}
  {{ if eq . "bar" }}
    {{ continue }}
  {{ end }}
  <p>{{ . }}</p>
{{ end }}
```

Is rendered to:

```html
<p>foo</p>
<p>baz</p>
```

{{% include "/_common/functions/go-template/text-template.md" %}}
