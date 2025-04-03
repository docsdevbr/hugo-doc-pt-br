---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: OutputFormats
description: Returns a slice of OutputFormat objects, each representing one of the output formats enabled for the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: '[]OutputFormat'
    signatures: [PAGE.OutputFormats]
---

{{% glossary-term "output format" %}}

The `OutputFormats` method on a `Page` object returns a slice of `OutputFormat` objects, each representing one of the output formats enabled for the given page. See&nbsp;[details](/configuration/output-formats/).

## Methods

{{% include "/_common/methods/page/output-format-methods.md" %}}

## Example

To link to the RSS feed for the current page:

```go-html-template
{{ with .OutputFormats.Get "rss" }}
  <a href="{{ .RelPermalink }}">RSS Feed</a>
{{ end }}
```

On the site's home page, Hugo renders this to:

```html
<a href="/index.xml">RSS Feed</a>
```

Please see the [link to output formats] section to understand the importance of the construct above.

[link to output formats]: /configuration/output-formats/#link-to-output-formats
