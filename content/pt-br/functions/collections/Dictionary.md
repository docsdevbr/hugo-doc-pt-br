---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.Dictionary
description: Returns a map composed of the given key-value pairs.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [dict]
    returnType: map[string]any
    signatures: ['collections.Dictionary [VALUE...]']
aliases: [/functions/dict]
---

Specify the key-value pairs as individual arguments:

```go-html-template
{{ $m := dict "a" 1 "b" 2 }}
```

The above produces this data structure:

```json
{
  "a": 1,
  "b": 2
}
```

To create an empty map:

```go-html-template
{{ $m := dict }}
```

Note that the `key` can be either a `string` or a `[]string`. The latter is useful to create a deeply nested structure, e.g.:

```go-html-template
{{ $m := dict (slice "a" "b" "c") "value" }}
```

The above produces this data structure:

```json
{
  "a": {
    "b": {
      "c": "value"
    }
  }
}
```
