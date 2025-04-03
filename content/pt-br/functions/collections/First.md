---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.First
description: Returns the given collection, limited to the first N elements.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [first]
    returnType: any
    signatures: [collections.First N COLLECTION]
aliases: [/functions/first]
---

```go-html-template
{{ range first 5 .Pages }}
  {{ .Render "summary" }}
{{ end }}
```

Set `N` to zero to return an empty collection.

```go-html-template
{{ $emptyPageCollection := first 0 .Pages }}
```

Use `first` and [`where`] together.

```go-html-template
{{ range where .Pages "Section" "articles" | first 5 }}
  {{ .Render "summary" }}
{{ end }}
```

[`where`]: /functions/collections/where/
