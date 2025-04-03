---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Page
description: Returns the Page object of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.Page
    signatures: [PAGE.Page]
---

This is a convenience method, useful within partial templates that are called from both [shortcodes](g) and page templates.

```go-html-template {file="layouts/shortcodes/foo.html"}
{{ partial "my-partial.html" . }}
```

When the shortcode calls the partial, it passes the current [context](g) (the dot). The context includes identifiers such as `Page`, `Params`, `Inner`, and `Name`.

```go-html-template {file="layouts/_default/single.html"}
{{ partial "my-partial.html" . }}
```

When the page template calls the partial, it also passes the current context (the dot). But in this case, the dot _is_ the `Page` object.

```go-html-template {file="layouts/partials/my-partial.html"}
The page title is: {{ .Page.Title }}
```

To handle both scenarios, the partial template must be able to access the `Page` object with `Page.Page`.

> [!note]
> And yes, that means you can do `.Page.Page.Page.Page.Title` too.
>
> But don't.
