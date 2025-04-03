---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Config
description: Returns a subset of the site configuration.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.SiteConfig
    signatures: [SITE.Config]
---

The `Config` method on a `Site` object provides access to a subset of the site configuration, specifically the `services` and `privacy` keys.

## Services

See [configure services](/configuration/services).

For example, to use Hugo's built-in Google Analytics template you must add a [Google tag ID]:

[Google tag ID]: https://support.google.com/tagmanager/answer/12326985?hl=en

{{< code-toggle file=hugo >}}
[services.googleAnalytics]
id = 'G-XXXXXXXXX'
{{< /code-toggle >}}

To access this value from a template:

```go-html-template
{{ .Site.Config.Services.GoogleAnalytics.ID }} → G-XXXXXXXXX
```

You must capitalize each identifier as shown above.

## Privacy

See [configure privacy](/configuration/privacy).

For example, to disable usage of the built-in YouTube shortcode:

{{< code-toggle file=hugo >}}
[privacy.youtube]
disable = true
{{< /code-toggle >}}

To access this value from a template:

```go-html-template
{{ .Site.Config.Privacy.YouTube.Disable }} → true
```

You must capitalize each identifier as shown above.
