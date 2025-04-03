---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Lastmod
description: Returns the last modification date of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [PAGE.Lastmod]
---

Set the last modification date in front matter:

{{< code-toggle file=content/news/article-1.md fm=true >}}
title = 'Article 1'
lastmod = 2023-10-19T00:40:04-07:00
{{< /code-toggle >}}

The last modification date is a [time.Time] value. Format and localize the value with the [`time.Format`] function, or use it with any of the [time methods].

```go-html-template
{{ .Lastmod | time.Format ":date_medium" }} → Oct 19, 2023
```

In the example above we explicitly set the last modification date in front matter. With Hugo's default configuration, the `Lastmod` method returns the front matter value. This behavior is configurable, allowing you to:

- Set the last modification date to the Author Date of the last Git commit for that file. See [`GitInfo`] for details.
- Set fallback values if the last modification date is not defined in front matter.

Learn more about [date configuration].

[`gitinfo`]: /methods/page/gitinfo/
[`time.format`]: /functions/time/format/
[date configuration]: /configuration/front-matter/#dates
[time methods]: /methods/time/
[time.time]: https://pkg.go.dev/time#Time
