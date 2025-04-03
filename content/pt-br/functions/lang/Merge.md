---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: lang.Merge
description: Merge missing translations from other languages.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: any
    signatures: [lang.Merge FROM TO]
aliases: [/functions/lang.merge]
---

As an example:

```sh
{{ $pages := .Site.RegularPages | lang.Merge $frSite.RegularPages | lang.Merge $enSite.RegularPages }}
```

Will "fill in the gaps" in the current site with, from left to right, content from the French site, and lastly the English.

A more practical example is to fill in the missing translations from the other languages:

```sh
{{ $pages := .Site.RegularPages }}
{{ range .Site.Home.Translations }}
{{ $pages = $pages | lang.Merge .Site.RegularPages }}
{{ end }}
 ```
