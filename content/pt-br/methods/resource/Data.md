---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Data
description: Applicable to resources returned by the resources.GetRemote function, returns information from the HTTP response.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: map
    signatures: [RESOURCE.Data]
---

The `Data` method on a resource returned by the [`resources.GetRemote`] function returns information from the HTTP response.

[`resources.GetRemote`]: /functions/resources/getremote/

## Example

```go-html-template
{{ $url := "https://example.org/images/a.jpg" }}
{{ $opts := dict "responseHeaders" (slice "Server") }}
{{ with try (resources.GetRemote $url) }}
  {{ with .Err }}
    {{ errorf "%s" . }}
  {{ else with .Value }}
    {{ with .Data }}
      {{ .ContentLength }} → 42764
      {{ .ContentType }} → image/jpeg
      {{ .Headers }} → map[Server:[Netlify]]
      {{ .Status }} → 200 OK
      {{ .StatusCode }} → 200
      {{ .TransferEncoding }} → []
    {{ end }}
  {{ else }}
    {{ errorf "Unable to get remote resource %q" $url }}
  {{ end }}
{{ end }}
```

## Methods

### ContentLength

(`int`) The content length in bytes.

### ContentType

(`string`) The content type.

### Headers

(`map[string][]string`) A map of response headers matching those requested in the [`responseHeaders`] option passed to the `resources.GetRemote` function. The header name matching is case-insensitive. In most cases there will be one value per header key.

### Status

(`string`) The HTTP status text.

### StatusCode

(`int`) The HTTP status code.

### TransferEncoding

(`string`) The transfer encoding.

[`resources.GetRemote`]: /functions/resources/getremote/
[`responseHeaders`]: /functions/resources/getremote/#responseheaders
