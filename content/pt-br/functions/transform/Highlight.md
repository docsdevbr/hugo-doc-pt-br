---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.Highlight
description: Renders code with a syntax highlighter.
categories: []
keywords: [highlight]
params:
  functions_and_methods:
    aliases: [highlight]
    returnType: template.HTML
    signatures: ['transform.Highlight CODE LANG [OPTIONS]']
aliases: [/functions/highlight]
---

The `highlight` function uses the [Chroma] syntax highlighter, supporting over 200 languages with more than 40 [highlighting styles].

[chroma]: https://github.com/alecthomas/chroma
[highlighting styles]: /quick-reference/syntax-highlighting-styles/

## Arguments

The `transform.Highlight` shortcode takes three arguments.

CODE
: (`string`) The code to highlight.

LANG
: (`string`) The language of the code to highlight. Choose from one of the [supported languages]. This value is case-insensitive.

OPTIONS
: (`map or string`) A map or comma-separated key-value pairs wrapped in quotation marks. Set default values for each option in your [site configuration]. The key names are case-insensitive.

[site configuration]: /configuration/markup#highlight
[supported languages]: /content-management/syntax-highlighting#languages

## Examples

```go-html-template
{{ $input := `fmt.Println("Hello World!")` }}
{{ transform.Highlight $input "go" }}

{{ $input := `console.log('Hello World!');` }}
{{ $lang := "js" }}
{{ transform.Highlight $input $lang "lineNos=table, style=api" }}

{{ $input := `echo "Hello World!"` }}
{{ $lang := "bash" }}
{{ $opts := dict "lineNos" "table" "style" "dracula" }}
{{ transform.Highlight $input $lang $opts }}
```

## Options

{{% include "_common/syntax-highlighting-options.md" %}}
