---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: crypto.HMAC
description: Returns a cryptographic hash that uses a key to sign a message.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [hmac]
    returnType: string
    signatures: ['crypto.HMAC HASH_TYPE KEY MESSAGE [ENCODING]']
aliases: [/functions/hmac]
---

Set the `HASH_TYPE` argument to `md5`, `sha1`, `sha256`, or `sha512`.

Set the optional `ENCODING` argument to either `hex` (default) or `binary`.

```go-html-template
{{ hmac "sha256" "Secret key" "Secret message" }}
5cceb491f45f8b154e20f3b0a30ed3a6ff3027d373f85c78ffe8983180b03c84

{{ hmac "sha256" "Secret key" "Secret message" "hex" }}
5cceb491f45f8b154e20f3b0a30ed3a6ff3027d373f85c78ffe8983180b03c84

{{ hmac "sha256" "Secret key" "Secret message" "binary" | base64Encode }}
XM60kfRfixVOIPOwow7Tpv8wJ9Nz+Fx4/+iYMYCwPIQ=
```
