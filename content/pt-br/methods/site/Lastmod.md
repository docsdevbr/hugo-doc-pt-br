---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Lastmod
description: Returns the last modification date of site content.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [SITE.Lastmod]
---

{{< new-in 0.123.0 />}}

The `Lastmod` method on a `Site` object returns a [`time.Time`] value. Use this with time [functions] and [methods]. For example:

```go-html-template
{{ .Site.Lastmod | time.Format ":date_long" }} → January 31, 2024

```

[`time.Time`]: https://pkg.go.dev/time#Time
[functions]: /functions/time/
[methods]: /methods/time/
