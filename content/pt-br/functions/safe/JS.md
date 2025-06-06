---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: safe.JS
description: Declares the given string as a safe JavaScript expression.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [safeJS]
    returnType: template.JS
    signatures: [safe.JS INPUT]
aliases: [/functions/safejs]
---

## Introduction

{{% include "/_common/functions/go-html-template-package.md" %}}

## Usage

Use the `safe.JS` function to encapsulate a known safe EcmaScript5 Expression.

Template authors are responsible for ensuring that typed expressions do not break the intended precedence and that there is no statement/expression ambiguity as when passing an expression like `{ foo: bar() }\n['foo']()`, which is both a valid Expression and a valid Program with a very different meaning.

Use of this type presents a security risk: the encapsulated content should come from a trusted source, as it will be included verbatim in the template output.

Using the `safe.JS` function to include valid but untrusted JSON is not safe. A safe alternative is to parse the JSON with the [`transform.Unmarshal`] function and then pass the resultant object into the template, where it will be converted to sanitized JSON when presented in a JavaScript context.

[`transform.Unmarshal`]: /functions/transform/unmarshal/

See the [Go documentation] for details.

[Go documentation]: https://pkg.go.dev/html/template#JS

## Example

Without a safe declaration:

```go-html-template
{{ $js := "x + y" }}
<script>const a = {{ $js }}</script>
```

Hugo renders the above to:

```html
<script>const a = "x + y"</script>
```

To declare the string as safe:

```go-html-template
{{ $js := "x + y" }}
<script>const a = {{ $js | safeJS }}</script>
```

Hugo renders the above to:

```html
<script>const a = x + y</script>
```
