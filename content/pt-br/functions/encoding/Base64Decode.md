---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: encoding.Base64Decode
description: Returns the base64 decoding of the given content.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [base64Decode]
    returnType: string
    signatures: [encoding.Base64Decode INPUT]
aliases: [/functions/base64Decode]
---

```go-html-template
{{ "SHVnbw==" | base64Decode }} → Hugo
```

Use the `base64Decode` function to decode responses from APIs. For example, the result of this call to GitHub's API contains the base64-encoded representation of the repository's README file:

```text
https://api.github.com/repos/gohugoio/hugo/readme
```

To retrieve and render the content:

```go-html-template
{{ $url := "https://api.github.com/repos/gohugoio/hugo/readme" }}
{{ with try (resources.GetRemote $url) }}
  {{ with .Err }}
    {{ errorf "%s" . }}
  {{ else with .Value }}
    {{ with . | transform.Unmarshal }}
      {{ .content | base64Decode | markdownify }}
    {{ end }}
  {{ else }}
    {{ errorf "Unable to get remote resource %q" $url }}
  {{ end }}
{{ end }}
```
