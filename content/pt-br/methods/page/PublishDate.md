---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: PublishDate
description: Returns the publish date of the given page.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: time.Time
    signatures: [PAGE.PublishDate]
---

By default, Hugo excludes pages with future publish dates when building your site. To include future pages, use the `--buildFuture` command line flag.

Set the publish date in front matter:

{{< code-toggle file=content/news/article-1.md fm=true >}}
title = 'Article 1'
publishDate = 2023-10-19T00:40:04-07:00
{{< /code-toggle >}}

The publish date is a [time.Time] value. Format and localize the value with the [`time.Format`] function, or use it with any of the [time methods].

```go-html-template
{{ .PublishDate | time.Format ":date_medium" }} → Oct 19, 2023
```

In the example above we explicitly set the publish date in front matter. With Hugo's default configuration, the `PublishDate` method returns the front matter value. This behavior is configurable, allowing you to set fallback values if the publish date is not defined in front matter. See&nbsp;[details].

[`time.Format`]: /functions/time/format/
[details]: /configuration/front-matter/#dates
[time methods]: /methods/time/
[time.Time]: https://pkg.go.dev/time#Time
