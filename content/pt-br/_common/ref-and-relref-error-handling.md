---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

_comment: Do not remove front matter.
---

By default, Hugo will throw an error and fail the build if it cannot resolve the path. You can change this to a warning in your site configuration, and specify a URL to return when the path cannot be resolved.

{{< code-toggle file=hugo >}}
refLinksErrorLevel = 'warning'
refLinksNotFoundURL = '/some/other/url'
{{< /code-toggle >}}
