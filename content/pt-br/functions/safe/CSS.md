---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: safe.CSS
description: Declares the given string as a safe CSS string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [safeCSS]
    returnType: template.CSS
    signatures: [safe.CSS INPUT]
aliases: [/functions/safecss]
---

## Introduction

{{% include "/_common/functions/go-html-template-package.md" %}}

## Usage

Use the `safe.CSS` function to encapsulate known safe content that matches any of:

1. The CSS3 stylesheet production, such as `p { color: purple }`.
1. The CSS3 rule production, such as `a[href=~"https:"].foo#bar`.
1. CSS3 declaration productions, such as `color: red; margin: 2px`.
1. The CSS3 value production, such as `rgba(0, 0, 255, 127)`.

Use of this type presents a security risk: the encapsulated content should come from a trusted source, as it will be included verbatim in the template output.

See the [Go documentation] for details.

## Example

Without a safe declaration:

```go-html-template
{{ $style := "color: red;" }}
<p style="{{ $style }}">foo</p>
```

Hugo renders the above to:

```html
<p style="ZgotmplZ">foo</p>
```

> [!note]
> `ZgotmplZ` is a special value that indicates that unsafe content reached a CSS or URL context at runtime.

To declare the string as safe:

```go-html-template
{{ $style := "color: red;" }}
<p style="{{ $style | safeCSS }}">foo</p>
```

Hugo renders the above to:

```html
<p style="color: red;">foo</p>
```

[Go documentation]: https://pkg.go.dev/html/template#CSS
