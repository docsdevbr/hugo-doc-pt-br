---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: os.FileExists
description: Reports whether the file or directory exists.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [fileExists]
    returnType: bool
    signatures: [os.FileExists PATH]
aliases: [/functions/fileexists]
---

The `os.FileExists` function attempts to resolve the path relative to the root of your project directory. If a matching file or directory is not found, it will attempt to resolve the path relative to the [`contentDir`](/configuration/all/#contentdir). A leading path separator (`/`) is optional.

With this directory structure:

```text
content/
├── about.md
├── contact.md
└── news/
    ├── article-1.md
    └── article-2.md
```

The function returns these values:

```go-html-template
{{ fileExists "content" }} → true
{{ fileExists "content/news" }} → true
{{ fileExists "content/news/article-1" }} → false
{{ fileExists "content/news/article-1.md" }} → true
{{ fileExists "news" }} → true
{{ fileExists "news/article-1" }} → false
{{ fileExists "news/article-1.md" }} → true
```
