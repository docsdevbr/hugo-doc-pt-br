---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Syntax highlighting styles
description: Highlight code examples using one of these styles.
categories: []
keywords: [highlight]
---

## Overview

Hugo provides several methods to add syntax highlighting to code examples:

- Use the [`transform.Highlight`] function within your templates
- Use the [`highlight`] shortcode with any [content format](g)
- Use fenced code blocks with the Markdown content format

Regardless of method, use any of the syntax highlighting styles below.

Set the default syntax highlighting style in your site configuration:

{{< code-toggle file=hugo >}}
[markup.highlight]
style = 'monokai'
{{< /code-toggle >}}

See [configure Markup](/configuration/markup/#highlight).

[`transform.Highlight`]: /functions/transform/highlight/
[`highlight`]: /shortcodes/highlight/
[fenced code blocks]: /content-management/syntax-highlighting/#fenced-code-blocks

## Styles

This gallery demonstrates the application of each syntax highlighting style with code examples written in different programming languages.

{{% syntax-highlighting-styles %}}
