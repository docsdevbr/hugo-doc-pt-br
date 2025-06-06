---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Chomp
description: Returns the given string, removing all trailing newline characters and carriage returns.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [chomp]
    returnType: any
    signatures: [strings.Chomp STRING]
aliases: [/functions/chomp]
---

If the argument is of type `template.HTML`, returns `template.HTML`, else returns a `string`.

```go-html-template
{{ chomp "foo\n" }} → foo
{{ chomp "foo\n\n" }} → foo

{{ chomp "foo\r\n" }} → foo
{{ chomp "foo\r\n\r\n" }} → foo
```
