---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: urls.Ref
description: Returns the absolute URL of the page with the given path, language, and output format.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [ref]
    returnType: string
    signatures:
      - urls.Ref PAGE PATH
      - urls.Ref PAGE OPTIONS
aliases: [/functions/ref]
---

## Usage

The `ref` function takes two arguments:

1. The context for resolving relative paths (typically the current page).
1. Either the target page's path or an options map (see below).

## Options

{{% include "_common/ref-and-relref-options.md" %}}

## Examples

The following examples show the rendered output for a page on the English version of the site:

```go-html-template
{{ ref . "/books/book-1" }} → https://example.org/en/books/book-1/

{{ $opts := dict "path" "/books/book-1" }}
{{ ref . $opts }} → https://example.org/en/books/book-1/

{{ $opts := dict "path" "/books/book-1" "lang" "de" }}
{{ ref . $opts }} → https://example.org/de/books/book-1/

{{ $opts := dict "path" "/books/book-1" "lang" "de" "outputFormat" "json" }}
{{ ref . $opts }} → https://example.org/de/books/book-1/index.json
```

## Error handling

{{% include "_common/ref-and-relref-error-handling.md" %}}
