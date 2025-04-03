---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: BaseURL
description: Returns the base URL as defined in the site configuration.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [SITE.BaseURL]
---

Site configuration:

{{< code-toggle file=hugo >}}
baseURL = 'https://example.org/docs/'
{{< /code-toggle >}}

Template:

```go-html-template
{{ .Site.BaseURL }} → https://example.org/docs/
```

> [!note]
> There is almost never a good reason to use this method in your templates. Its usage tends to be fragile due to misconfiguration.
>
> Use the [`absURL`], [`absLangURL`], [`relURL`], or [`relLangURL`] functions instead.

[`absLangURL`]: /functions/urls/absLangURL/
[`absURL`]: /functions/urls/absURL/
[`relLangURL`]: /functions/urls/relLangURL/
[`relURL`]: /functions/urls/relURL/
