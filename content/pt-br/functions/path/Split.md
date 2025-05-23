---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: path.Split
description: Replaces path separators with slashes (`/`) and splits the resulting path immediately following the final slash, separating it into a directory and file name component.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: paths.DirFile
    signatures: [path.Split PATH]
aliases: [/functions/path.split]
---

If there is no slash in the given path, `path.Split` returns an empty directory, and file set to path. The returned values have the property that path = dir+file.

```go-html-template
{{ $dirFile := path.Split "a/news.html" }}
{{ $dirFile.Dir }} → a/
{{ $dirFile.File }} → news.html

{{ $dirFile := path.Split "news.html" }}
{{ $dirFile.Dir }} → "" (empty string)
{{ $dirFile.File }} → news.html

{{ $dirFile := path.Split "a/b/c" }}
{{ $dirFile.Dir }} → a/b/
{{ $dirFile.File }} → c
```
