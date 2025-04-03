---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Keywords
description: Returns a slice of keywords as defined in front matter.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: '[]string'
    signatures: [PAGE.Keywords]
---

By default, Hugo evaluates the keywords when creating collections of [related content].

[related content]: /content-management/related-content/

{{< code-toggle file=content/recipes/sushi.md fm=true >}}
title = 'How to make spicy tuna hand rolls'
keywords = ['tuna','sriracha','nori','rice']
{{< /code-toggle >}}

To list the keywords within a template:

```go-html-template
{{ range .Keywords }}
  {{ . }}
{{ end }}
```

Or use the [delimit] function:

```go-html-template
{{ delimit .Keywords ", " ", and " }} → tuna, sriracha, nori, and rice
```

[delimit]: /functions/collections/delimit/

Keywords are also a useful [taxonomy]:

{{< code-toggle file=hugo >}}
[taxonomies]
tag = 'tags'
keyword = 'keywords'
category = 'categories'
{{< /code-toggle >}}

[taxonomy]: /content-management/taxonomies/
