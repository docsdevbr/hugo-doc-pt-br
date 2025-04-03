---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.Markdownify
description: Renders Markdown to HTML.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [markdownify]
    returnType: template.HTML
    signatures: [transform.Markdownify INPUT]
aliases: [/functions/markdownify]
---

```go-html-template
<h2>{{ .Title | markdownify }}</h2>
```

If the resulting HTML is a single paragraph, Hugo removes the wrapping `p` tags to produce inline HTML as required per the example above.

To keep the wrapping `p` tags for a single paragraph, use the [`RenderString`] method on the `Page` object, setting the `display` option to `block`.

> [!note]
> Although the `markdownify` function honors [Markdown render hooks] when rendering Markdown to HTML, use the `RenderString` method instead of `markdownify` if a render hook accesses `.Page` context. See issue [#9692] for details.

[#9692]: https://github.com/gohugoio/hugo/issues/9692
[`RenderString`]: /methods/page/renderstring/
[Markdown render hooks]: /render-hooks/
