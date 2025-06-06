---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: collections.IsSet
description: Reports whether the key exists within the collection.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [isset]
    returnType: bool
    signatures: [collections.IsSet COLLECTION KEY]
aliases: [/functions/isset]
---

For example, consider this site configuration:

{{< code-toggle file=hugo >}}
[params]
showHeroImage = false
{{< /code-toggle >}}

It the value of `showHeroImage` is `true`, we can detect that it exists using either `if` or `with`:

```go-html-template
{{ if site.Params.showHeroImage }}
  {{ site.Params.showHeroImage }} → true
{{ end }}

{{ with site.Params.showHeroImage }}
  {{ . }} → true
{{ end }}
```

But if the value of `showHeroImage` is `false`, we can't use either `if` or `with` to detect its existence. In this case, you must use the `isset` function:

```go-html-template
{{ if isset site.Params "showheroimage" }}
  <p>The showHeroImage parameter is set to {{ site.Params.showHeroImage }}.<p>
{{ end }}
```

> [!note]
> When using the `isset` function you must reference the key using lower case. See the previous example.
