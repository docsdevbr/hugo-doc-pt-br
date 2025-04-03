---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Title
description: Returns the title of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [PAGE.Title]
---

With pages backed by a file, the `Title` method returns the `title` field as defined in front matter:

{{< code-toggle file=content/about.md fm=true >}}
title = 'About us'
{{< /code-toggle >}}

```go-html-template
{{ .Title }} → About us
```

With section, taxonomy, and term pages not backed by a file, the `Title` method returns the section name, capitalized and pluralized. You can disable these transformations by setting [`capitalizeListTitles`] and [`pluralizeListTitles`] in your site configuration. For example:

{{< code-toggle file=hugo >}}
capitalizeListTitles = false
pluralizeListTitles = false
{{< /code-toggle >}}

You can change the capitalization style in your site configuration to one of `ap`, `chicago`, `go`, `firstupper`, or `none`. For example:

{{< code-toggle file=hugo >}}
titleCaseStyle = "firstupper"
{{< /code-toggle >}}

 See&nbsp;[details].

[`capitalizeListTitles`]: /configuration/all/#capitalizelisttitles
[`pluralizeListTitles`]: /configuration/all/#pluralizelisttitles
[details]: /configuration/all/#title-case-style
