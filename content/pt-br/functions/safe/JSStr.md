---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: safe.JSStr
description: Declares the given string as a safe JavaScript string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [safeJSStr]
    returnType: template.JSStr
    signatures: [safe.JSStr INPUT]
aliases: [/functions/safejsstr]
---

## Introduction

{{% include "/_common/functions/go-html-template-package.md" %}}

## Usage

Use the `safe.JSStr` function to encapsulate a sequence of characters meant to be embedded between quotes in a JavaScript expression.

Use of this type presents a security risk: the encapsulated content should come from a trusted source, as it will be included verbatim in the template output.

See the [Go documentation] for details.

[Go documentation]: https://pkg.go.dev/html/template#JSStr

## Example

Without a safe declaration:

```go-html-template
{{ $title := "Lilo & Stitch" }}
<script>
  const a = "Title: " + {{ $title }};
</script>
```

Hugo renders the above to:

```html
<script>
  const a = "Title: " + "Lilo \u0026 Stitch";
</script>
```

To declare the string as safe:

```go-html-template
{{ $title := "Lilo & Stitch" }}
<script>
  const a = "Title: " + {{ $title | safeJSStr }};
</script>
```

Hugo renders the above to:

```html
<script>
  const a = "Title: " + "Lilo & Stitch";
</script>
```
