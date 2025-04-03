---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Section
description: Returns the name of the top-level section in which the given page resides.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Section]
---

{{% glossary-term section %}}

With this content structure:

```text
content/
├── lessons/
│   ├── math/
│   │   ├── _index.md
│   │   ├── lesson-1.md
│   │   └── lesson-2.md
│   └── _index.md
└── _index.md
```

When rendering lesson-1.md:

```go-html-template
{{ .Section }} → lessons
```

In the example above "lessons" is the top-level section.

The `Section` method is often used with the [`where`] function to build a page collection.

```go-html-template
{{ range where .Site.RegularPages "Section" "lessons" }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

This is similar to using the [`Type`] method with the `where` function

```go-html-template
{{ range where .Site.RegularPages "Type" "lessons" }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

However, if the `type` field in front matter has been defined on one or more pages, the page collection based on `Type` will be different than the page collection based on `Section`.

[`where`]: /functions/collections/where/
[`Type`]: /methods/page/type/
