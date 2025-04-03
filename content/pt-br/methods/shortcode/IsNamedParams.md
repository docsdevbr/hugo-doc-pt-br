---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: IsNamedParams
description: Reports whether the shortcode call uses named arguments.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [SHORTCODE.IsNamedParams]
---

To support both positional and named arguments when calling a shortcode, use the `IsNamedParams` method to determine how the shortcode was called.

With this shortcode template:

```go-html-template {file="layouts/shortcodes/myshortcode.html"}
{{ if .IsNamedParams }}
  {{ printf "%s %s." (.Get "greeting") (.Get "firstName") }}
{{ else }}
  {{ printf "%s %s." (.Get 0) (.Get 1) }}
{{ end }}
```

Both of these calls return the same value:

```text {file="content/about.md"}
{{</* myshortcode greeting="Hello" firstName="world" */>}}
{{</* myshortcode "Hello" "world" */>}}
```
