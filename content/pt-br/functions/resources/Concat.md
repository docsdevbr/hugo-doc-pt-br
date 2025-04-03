---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: resources.Concat
description: Returns a concatenated slice of resources.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: resource.Resource
    signatures: ['resources.Concat TARGETPATH [RESOURCE...]']
---

The `resources.Concat` function returns a concatenated slice of resources, caching the result using the target path as its cache key. Each resource must have the same [media type].

Hugo publishes the resource to the target path when you call its [`Publish`], [`Permalink`], or [`RelPermalink`] method.

[media type]: https://en.wikipedia.org/wiki/Media_type
[`publish`]: /methods/resource/publish/
[`permalink`]: /methods/resource/permalink/
[`relpermalink`]: /methods/resource/relpermalink/

```go-html-template
{{ $plugins := resources.Get "js/plugins.js" }}
{{ $global := resources.Get "js/global.js" }}
{{ $js := slice $plugins $global | resources.Concat "js/bundle.js" }}
```
