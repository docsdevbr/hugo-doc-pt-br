---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: HasShortcode
description: Reports whether the given shortcode is called by the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: bool
    signatures: [PAGE.HasShortcode NAME]
---

By example, let's use [Plotly] to render a chart:

[Plotly]: https://plotly.com/javascript/

```text {file="content/example.md"}
{{</* plotly */>}}
{
  "data": [
    {
      "x": ["giraffes", "orangutans", "monkeys"],
      "y": [20, 14, 23],
      "type": "bar"
    }
  ],
}
{{</* /plotly */>}}
```

The shortcode is simple:

```go-html-template {file="layouts/shortcodes/plotly.html"}
{{ $id := printf "plotly-%02d" .Ordinal }}
<div id="{{ $id }}"></div>
<script>
  Plotly.newPlot(document.getElementById({{ $id }}), {{ .Inner | safeJS }});
</script>
```

Now we can selectively load the required JavaScript on pages that call the "plotly" shortcode:

```go-html-template {file="layouts/_default/baseof.html"}
<head>
  ...
  {{ if .HasShortcode "plotly" }}
    <script src="https://cdn.plot.ly/plotly-2.28.0.min.js"></script>
  {{ end }}
  ...
</head>
```
