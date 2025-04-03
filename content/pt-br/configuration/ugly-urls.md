---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Configure ugly URLs
linkTitle: Ugly URLs
description: Configure ugly URLs.
categories: []
keywords: []
---

{{% glossary-term "ugly url" %}}&nbsp;For example:

```text
https://example.org/section/article.html
```

In its default configuration, Hugo generates [pretty URLs](g). For example:
```text
https://example.org/section/article/
```

This is the default configuration:

{{< code-toggle config=uglyURLs />}}

To generate ugly URLs for the entire site:

{{< code-toggle file=hugo >}}
uglyURLs = true
{{< /code-toggle >}}

To generate ugly URLs for specific sections of your site:

{{< code-toggle file=hugo >}}
[uglyURLs]
books = true
films = false
{{< /code-toggle >}}
