---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: fmt.Print
description: Prints the default representation of the given arguments using the standard `fmt.Print` function.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [print]
    returnType: string
    signatures: [fmt.Print INPUT]
aliases: [/functions/print]
---

```go-html-template
{{ print "foo" }} → foo
{{ print "foo" "bar" }} → foobar
{{ print (slice 1 2 3) }} → [1 2 3]
```
