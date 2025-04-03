---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.HighlightCodeBlock
description: Highlights code received in context within a code block render hook.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: highlight.HighlightResult 
    signatures: ['transform.HighlightCodeBlock CONTEXT [OPTIONS]']
---

This function is only useful within a code block render hook.

Given the context passed into a code block render hook, `transform.HighlightCodeBlock` returns a `HighlightResult` object with two methods.

.Wrapped
: (`template.HTML`) Returns highlighted code wrapped in `<div>`, `<pre>`, and `<code>` elements. This is identical to the value returned by the transform.Highlight function.

.Inner
: (`template.HTML`) Returns highlighted code without any wrapping elements, allowing you to create your own wrapper.

```go-html-template
{{ $result := transform.HighlightCodeBlock . }}
{{ $result.Wrapped }}
```

To override the default [highlighting options]:

```go-html-template
{{ $opts := merge .Options (dict "linenos" true) }}
{{ $result := transform.HighlightCodeBlock . $opts }}
{{ $result.Wrapped }}
```

[highlighting options]: /functions/transform/highlight/#options
