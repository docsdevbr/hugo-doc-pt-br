---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: safe.HTML
description: Declares the given string as a safeHTML string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [safeHTML]
    returnType: template.HTML
    signatures: [safe.HTML INPUT]
aliases: [/functions/safehtml]
---

## Introduction

{{% include "/_common/functions/go-html-template-package.md" %}}

## Usage

Use the `safe.HTML` function to encapsulate a known safe HTML document fragment. It should not be used for HTML from a third-party, or HTML with unclosed tags or comments.

Use of this type presents a security risk: the encapsulated content should come from a trusted source, as it will be included verbatim in the template output.

See the [Go documentation] for details.

[Go documentation]: https://pkg.go.dev/html/template#HTML

## Example

Without a safe declaration:

```go-html-template
{{ $html := "<em>emphasized</em>" }}
{{ $html }}
```

Hugo renders the above to:

```html
&lt;em&gt;emphasized&lt;/em&gt;
```

To declare the string as safe:

```go-html-template
{{ $html := "<em>emphasized</em>" }}
{{ $html | safeHTML }}
```

Hugo renders the above to:

```html
<em>emphasized</em>
```
