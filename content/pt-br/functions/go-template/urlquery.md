---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: urlquery
description: Returns the escaped value of the textual representation of its arguments in a form suitable for embedding in a URL query.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: string
    signatures: ['urlquery VALUE [VALUE...]']
aliases: [/functions/urlquery]
---

This template code:

```go-html-template
{{ $u := urlquery "https://" "example.com" | safeURL }}
<a href="https://example.org?url={{ $u }}">Link</a>
```

Is rendered to:

```html
<a href="https://example.org?url=https%3A%2F%2Fexample.com">Link</a>
```

{{% include "/_common/functions/go-template/text-template.md" %}}
