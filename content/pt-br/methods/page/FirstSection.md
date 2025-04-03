---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: FirstSection
description: Returns the Page object of the top-level section of which the given page is a descendant.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Page
    signatures: [PAGE.FirstSection]
---

{{% glossary-term section %}}

> [!note]
> When called on the home page, the `FirstSection` method returns the `Page` object of the home page itself.

Consider this content structure:

```text
content/
├── auctions/
│   ├── 2023-11/
│   │   ├── _index.md     <-- first section: auctions
│   │   ├── auction-1.md
│   │   └── auction-2.md  <-- first section: auctions
│   ├── 2023-12/
│   │   ├── _index.md     
│   │   ├── auction-3.md
│   │   └── auction-4.md
│   ├── _index.md         <-- first section: auctions
│   ├── bidding.md
│   └── payment.md        <-- first section: auctions
├── books/
│   ├── _index.md         <-- first section: books
│   ├── book-1.md
│   └── book-2.md         <-- first section: books
├── films/
│   ├── _index.md         <-- first section: films
│   ├── film-1.md
│   └── film-2.md         <-- first section: films
└── _index.md             <-- first section: home
```

To link to the top-level section of which the current page is a descendant:

```go-html-template
<a href="{{ .FirstSection.RelPermalink }}">{{ .FirstSection.LinkTitle }}</a>
```
