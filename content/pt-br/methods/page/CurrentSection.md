---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: CurrentSection
description: Returns the Page object of the section in which the given page resides.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Page
    signatures: [PAGE.CurrentSection]
---

{{% glossary-term section %}}

> [!note]
> The current section of a [section page](g), [taxonomy page](g), [term page](g), or the home page, is itself.

Consider this content structure:

```text
content/
├── auctions/
│   ├── 2023-11/
│   │   ├── _index.md     <-- current section: 2023-11
│   │   ├── auction-1.md
│   │   └── auction-2.md  <-- current section: 2023-11
│   ├── 2023-12/
│   │   ├── _index.md     
│   │   ├── auction-3.md
│   │   └── auction-4.md
│   ├── _index.md         <-- current section: auctions
│   ├── bidding.md
│   └── payment.md        <-- current section: auctions
├── books/
│   ├── _index.md         <-- current section: books
│   ├── book-1.md
│   └── book-2.md         <-- current section: books
├── films/
│   ├── _index.md         <-- current section: films 
│   ├── film-1.md
│   └── film-2.md         <-- current section: films
└── _index.md             <-- current section: home
```

To create a link to the current section page:

```go-html-template
<a href="{{ .CurrentSection.RelPermalink }}">{{ .CurrentSection.LinkTitle }}</a>
```
