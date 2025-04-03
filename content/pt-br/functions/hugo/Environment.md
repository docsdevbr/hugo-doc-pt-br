---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: hugo.Environment
description: Returns the current running environment.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: [hugo.Environment]
---

The `hugo.Environment` function returns the current running [environment](g) as defined through the `--environment` command line flag.

```go-html-template
{{ hugo.Environment }} → production
```

Command line examples:

Command|Environment
:--|:--
`hugo`|`production`
`hugo --environment staging`|`staging`
`hugo server`|`development`
`hugo server --environment staging`|`staging`
