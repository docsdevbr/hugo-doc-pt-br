---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.KeyVals
description: Returns a KeyVals struct.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [keyVals]
    returnType: types.KeyValues
    signatures: [collections.KeyVals KEY VALUE...]
aliases: [/functions/keyvals]
---

The primary application for this function is the definition of the `namedSlices` value in the options map passed to the [`Related`] method on the `Pages` object.

[`Related`]: /methods/pages/related/

See [related content](/content-management/related-content/).

```go-html-template
{{ $kv := keyVals "foo" "a" "b" "c" }}
```

The resulting data structure is:

```json
{
  "Key": "foo",
  "Values": [
    "a",
    "b",
    "c"
  ]
}
```

To extract the key and values:

```go-html-template
{{ $kv.Key }} → foo
{{ $kv.Values }} → [a b c]
```
