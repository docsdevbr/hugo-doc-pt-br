---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: else
description: Begins an alternate block for if, with, and range statements.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType:
    signatures: [else VALUE]
---

Use with the [`if`] statement:

```go-html-template
{{ $var := "foo" }}
{{ if $var }}
  {{ $var }} → foo
{{ else }}
  {{ print "var is falsy" }}
{{ end }}
```

Use with the [`with`] statement:

```go-html-template
{{ $var := "foo" }}
{{ with $var }}
  {{ . }} → foo
{{ else }}
  {{ print "var is falsy" }}
{{ end }}
```

Use with the [`range`] statement:

```go-html-template
{{ $var := slice 1 2 3 }}
{{ range $var }}
  {{ . }} → 1 2 3 
{{ else }}
  {{ print "var is falsy" }}
{{ end }}
```

Use `else if` to check multiple conditions.

```go-html-template
{{ $var := 12 }}
{{ if eq $var 6 }}
  {{ print "var is 6" }}
{{ else if eq $var 7 }}
  {{ print "var is 7" }}
{{ else if eq $var 42 }}
  {{ print "var is 42" }}
{{ else }}
  {{ print "var is something else" }}
{{ end }}
```

{{% include "/_common/functions/go-template/text-template.md" %}}

[`if`]: /functions/go-template/if/
[`with`]: /functions/go-template/with/
[`range`]: /functions/go-template/range/
