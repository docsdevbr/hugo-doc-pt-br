---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: crypto.MD5
description: Hashes the given input and returns its MD5 checksum encoded to a hexadecimal string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [md5]
    returnType: string
    signatures: [crypto.MD5 INPUT]
aliases: [/functions/md5]
---

```go-html-template
{{ md5 "Hello world" }} → 3e25960a79dbc69b674cd4ec67a72c62
```

This can be useful if you want to use [Gravatar](https://en.gravatar.com/) for generating a unique avatar:

```html
<img src="https://www.gravatar.com/avatar/{{ md5 "your@email.com" }}?s=100&d=identicon">
```
