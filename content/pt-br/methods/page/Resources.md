---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Resources
description: Returns a collection of page resources.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: resource.Resources
    signatures: [PAGE.Resources]
---

The `Resources` method on a `Page` object returns a collection of page resources. A page resource is a file within a [page bundle](g).

To work with global or remote resources, see the [`resources`] functions.

## Methods

### ByType

(`resource.Resources`) Returns a collection of page resources of the given [media type], or nil if none found. The media type is typically one of `image`, `text`, `audio`, `video`, or `application`.

```go-html-template
{{ range .Resources.ByType "image" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
{{ end }}
```

When working with global resources instead of page resources, use the [`resources.ByType`] function.

### Get

(`resource.Resource`) Returns a page resource from the given path, or nil if none found.

```go-html-template
{{ with .Resources.Get "images/a.jpg" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
{{ end }}
```

When working with global resources instead of page resources, use the [`resources.Get`] function.

### GetMatch

(`resource.Resource`) Returns the first page resource from paths matching the given [glob](g) pattern, or nil if none found.

```go-html-template
{{ with .Resources.GetMatch "images/*.jpg" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
{{ end }}
```

When working with global resources instead of page resources, use the [`resources.GetMatch`] function.

### Match

(`resource.Resources`) Returns a collection of page resources from paths matching the given [glob](g) pattern, or nil if none found.

```go-html-template
{{ range .Resources.Match "images/*.jpg" }}
  <img src="{{ .RelPermalink }}" width="{{ .Width }}" height="{{ .Height }}" alt="">
{{ end }}
```

When working with global resources instead of page resources, use the [`resources.Match`] function.

### Mount

{{< new-in 0.140.0 />}}

(`ResourceGetter`) Mounts the given resources from the two arguments base (`string`) to the given target path (`string`) and returns an object that implements [Get](#get). Note that leading slashes in target marks an absolute path. Relative target paths allows you to mount resources relative to another set, e.g. a [Page bundle](/content-management/page-bundles/):

```go-html-template
{{ $common := resources.Match "/js/headlessui/*.*" }}
{{ $importContext := (slice $.Page ($common.Mount "/js/headlessui" ".")) }}
```

This method is currently only useful in [js.Batch](/functions/js/batch/#import-context).

## Pattern matching

With the `GetMatch` and `Match` methods, Hugo determines a match using a case-insensitive [glob](g) pattern.

{{% include "/_common/glob-patterns.md" %}}

[`resources.ByType`]: /functions/resources/ByType/
[`resources.GetMatch`]: /functions/resources/ByType/
[`resources.Get`]: /functions/resources/ByType/
[`resources.Match`]: /functions/resources/ByType/
[`resources`]: /functions/resources/
[media type]: https://en.wikipedia.org/wiki/Media_type
