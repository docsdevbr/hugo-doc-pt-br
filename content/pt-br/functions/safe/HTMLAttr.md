---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: safe.HTMLAttr
description: Declares the given key-value pair as a safe HTML attribute.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [safeHTMLAttr]
    returnType: template.HTMLAttr
    signatures: [safe.HTMLAttr INPUT]
aliases: [/functions/safehtmlattr]
---

## Introduction

{{% include "/_common/functions/go-html-template-package.md" %}}

## Usage

Use the `safe.HTMLAttr` function to encapsulate an HTML attribute from a trusted source.

Use of this type presents a security risk: the encapsulated content should come from a trusted source, as it will be included verbatim in the template output.

See the [Go documentation] for details.

[Go documentation]: https://pkg.go.dev/html/template#HTMLAttr

## Example

Without a safe declaration:

```go-html-template
{{ with .Date }}
  {{ $humanDate := time.Format "2 Jan 2006" . }}
  {{ $machineDate := time.Format "2006-01-02T15:04:05-07:00" . }}
  <time datetime="{{ $machineDate }}">{{ $humanDate }}</time>
{{ end }}
```

Hugo renders the above to:

```html
<time datetime="2024-05-26T07:19:55&#43;02:00">26 May 2024</time>
```

To declare the key-value pair as safe:

```go-html-template
{{ with .Date }}
  {{ $humanDate := time.Format "2 Jan 2006" . }}
  {{ $machineDate := time.Format "2006-01-02T15:04:05-07:00" . }}
  <time {{ printf "datetime=%q" $machineDate | safeHTMLAttr }}>{{ $humanDate }}</time>
{{ end }}
```

Hugo renders the above to:

```html
<time datetime="2024-05-26T07:19:55+02:00">26 May 2024</time>
```
