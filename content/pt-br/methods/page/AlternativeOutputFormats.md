---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: AlternativeOutputFormats
description: Returns a slice of OutputFormat objects, excluding the current output format, each representing one of the output formats enabled for the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.OutputFormats
    signatures: [PAGE.AlternativeOutputFormats]
---

{{% glossary-term "output format" %}}

The `AlternativeOutputFormats` method on a `Page` object returns a slice of `OutputFormat` objects, excluding the current output format, each representing one of the output formats enabled for the given page. See&nbsp;[details](/configuration/output-formats/).

## Methods

{{% include "/_common/methods/page/output-format-methods.md" %}}

## Example

Generate a `link` element in the `<head>` of each page for each of the alternative output formats:

```go-html-template
<head>
  ...
  {{ $title := printf "%s | %s" .Title site.Title }}
  {{ if .IsHome }}
    {{ $title = site.Title }}
  {{ end }}
  {{ range .AlternativeOutputFormats }}
    {{ printf `<link rel=%q type=%q href=%q title=%q>` .Rel .MediaType.Type .Permalink $title | safeHTML }}
  {{ end }}
  ...
</head>
```

On the site's home page, Hugo renders this to:

```html
<link rel="alternate" type="application/rss+xml" href="https://example.org/index.xml" title="ABC Widgets, Inc.">
```
