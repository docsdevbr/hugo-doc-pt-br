---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: BundleType
description: Returns the bundle type of the given page, or an empty string if the page is not a page bundle.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.BundleType]
---

A page bundle is a directory that encapsulates both content and associated [resources](g). There are two types of page bundles: [leaf bundles](g) and [branch bundles](g). See&nbsp;[details](/content-management/page-bundles/).

The `BundleType` method on a `Page` object returns `branch` for branch bundles, `leaf` for leaf bundles, and an empty string if the page is not a page bundle.

```text
content/
├── films/
│   ├── film-1/
│   │   ├── a.jpg
│   │   └── index.md  <-- leaf bundle
│   ├── _index.md     <-- branch bundle
│   ├── b.jpg
│   ├── film-2.md
│   └── film-3.md
└── _index.md         <-- branch bundle
```

To get the value within a template:

```go-html-template
{{ .BundleType }}
```
