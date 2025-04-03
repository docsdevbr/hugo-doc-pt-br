---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Name
description: Returns the shortcode file name, excluding the file extension.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [SHORTCODE.Name]
---

The `Name` method is useful for error reporting. For example, if your shortcode requires a "greeting" argument:

```go-html-template {file="layouts/shortcodes/myshortcode.html"}
{{ $greeting := "" }}
{{ with .Get "greeting" }}
  {{ $greeting = . }}
{{ else }}
  {{ errorf "The %q shortcode requires a 'greeting' argument. See %s" .Name .Position }}
{{ end }}
```

In the absence of a "greeting" argument, Hugo will throw an error message and fail the build:

```text
ERROR The "myshortcode" shortcode requires a 'greeting' argument. See "/home/user/project/content/about.md:11:1"
```
