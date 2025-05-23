---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: LanguagePrefix
description: Returns the URL language prefix, if any, for the given site.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [SITE.LanguagePrefix]
---

Consider this site configuration:

{{< code-toggle file=hugo >}}
defaultContentLanguage = 'de'
defaultContentLanguageInSubdir = false

[languages.de]
languageCode = 'de-DE'
languageDirection = 'ltr'
languageName = 'Deutsch'
title = 'Projekt Dokumentation'
weight = 1

[languages.en]
languageCode = 'en-US'
languageDirection = 'ltr'
languageName = 'English'
title = 'Project Documentation'
weight = 2
{{< /code-toggle >}}

When visiting the German language site:

```go-html-template
{{ .Site.LanguagePrefix }} → ""
```

When visiting the English language site:

```go-html-template
{{ .Site.LanguagePrefix }} → /en
```

If you change `defaultContentLanguageInSubdir` to `true`, when visiting the German language site:

```go-html-template
{{ .Site.LanguagePrefix }} → /de
```

You may use the `LanguagePrefix` method with both monolingual and multilingual sites.
