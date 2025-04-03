---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: BuildDrafts
description: Reports whether the current build includes draft pages.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [SITE.BuildDrafts]
---

By default, draft pages are not published when building a site. You can change this behavior with a command line flag:

```sh
hugo --buildDrafts
```

Or by setting `buildDrafts` to `true` in your site configuration:

{{< code-toggle file=hugo >}}
buildDrafts = true
{{< /code-toggle >}}

Use the `BuildDrafts` method on a `Site` object to determine the current configuration:

```go-html-template
{{ .Site.BuildDrafts }} → true
```
