---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: MediaType
description: Returns a media type object for the given resource.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: media.Type
    signatures: [RESOURCE.MediaType]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

The `MediaType` method on a `Resource` object returns an object with additional methods.

## Methods

### Type

(`string`) The resource's media type.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .MediaType.Type }} → image/jpeg
{{ end }}
```

### MainType

(`string`) The main type of the resource's media type.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .MediaType.MainType }} → image
{{ end }}
```

### SubType

(`string`) The subtype of the resource's media type. This may or may not correspond to the file suffix.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .MediaType.SubType }} → jpeg
{{ end }}
```

### Suffixes

(`slice`) A slice of possible file suffixes for the resource's media type.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .MediaType.Suffixes }} → [jpg jpeg jpe jif jfif]
{{ end }}
```

### FirstSuffix.Suffix

(`string`) The first of the possible file suffixes for the resource's media type.

```go-html-template
{{ with resources.Get "images/a.jpg" }}
  {{ .MediaType.FirstSuffix.Suffix }} → jpg
{{ end }}
```
