---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Plain
description: Returns the rendered content of the given page, removing all HTML tags.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Plain]
---

The `Plain` method on a `Page` object renders Markdown and [shortcodes](g) to HTML, then strips the HTML [tags]. It does not strip HTML [entities].

To prevent Go's [html/template] package from escaping HTML entities, pass the result through the [`htmlUnescape`] function.

```go-html-template
{{ .Plain | htmlUnescape }}
```

[html/template]: https://pkg.go.dev/html/template
[entities]: https://developer.mozilla.org/en-US/docs/Glossary/Entity
[tags]: https://developer.mozilla.org/en-US/docs/Glossary/Tag
[`htmlUnescape`]: /functions/transform/htmlunescape/
