---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: RenderString
description: Renders markup to HTML.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: template.HTML
    signatures: ['PAGE.RenderString [OPTIONS] MARKUP']
aliases: [/functions/renderstring]
---

```go-html-template
{{ $s := "An *emphasized* word" }}
{{ $s | .RenderString }} → An <em>emphasized</em> word
```

This method takes an optional map of options:

display
: (`string`) Specify either `inline` or `block`. If `inline`, removes surrounding `p` tags from short snippets. Default is `inline`.

markup
: (`string`) Specify a [markup identifier] for the provided markup. Default is the `markup` front matter value, falling back to the value derived from the page's file extension.

Render with the default markup renderer:

```go-html-template
{{ $s := "An *emphasized* word" }}
{{ $s | .RenderString }} → An <em>emphasized</em> word

{{ $opts := dict "display" "block" }}
{{ $s | .RenderString $opts }} → <p>An <em>emphasized</em> word</p>
```

Render with [Pandoc]:

```go-html-template
{{ $s := "H~2~O" }}

{{ $opts := dict "markup" "pandoc" }}
{{ $s | .RenderString $opts }} → H<sub>2</sub>O

{{ $opts := dict "display" "block" "markup" "pandoc" }}
{{ .RenderString $opts $s }} → <p>H<sub>2</sub>O</p>
```

[markup identifier]: /content-management/formats/#classification
[pandoc]: https://www.pandoc.org/
