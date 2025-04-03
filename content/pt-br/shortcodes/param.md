---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Param shortcode
linkTitle: Param
description: Insert a parameter from front matter or site configuration into your content using the param shortcode.
categories: []
keywords: []
---

> [!note]
> To override Hugo's embedded `param` shortcode, copy the [source code] to a file with the same name in the `layouts/shortcodes` directory.

The `param` shortcode renders a parameter from front matter, falling back to a site parameter of the same name. The shortcode throws an error if the parameter does not exist.

```text {file="content/example.md"}
---
title: Example
date: 2025-01-15T23:29:46-08:00
params:
  color: red
  size: medium
---

We found a {{%/* param "color" */%}} shirt.
```

Hugo renders this to:

```html
<p>We found a red shirt.</p>
```

Access nested values by [chaining](g) the [identifiers](g):

```text
{{%/* param my.nested.param */%}}
```

[source code]: {{% eturl param %}}
