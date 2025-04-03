---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: GroupByPublishDate
description: Returns the given page collection grouped by publish date in descending order.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: page.PagesGroup
    signatures: ['PAGES.GroupByPublishDate LAYOUT [SORT]']
---

When grouping by publish date, the value is determined by your [site configuration], defaulting to the `publishDate` field in front matter.

The [layout string] has the same format as the layout string for the [`time.Format`] function. The resulting group key is [localized](g) for language and region.

[`time.Format`]: /functions/time/format/
[layout string]: #layout-string
[site configuration]: /configuration/front-matter/#dates

{{% include "/_common/methods/pages/group-sort-order.md" %}}

To group content by year and month:

```go-html-template
{{ range .Pages.GroupByPublishDate "January 2006" }}
  <p>{{ .Key }}</p>
  <ul>
    {{ range .Pages }}
      <li><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

To sort the groups in ascending order:

```go-html-template
{{ range .Pages.GroupByPublishDate "January 2006" "asc" }}
  <p>{{ .Key }}</p>
  <ul>
    {{ range .Pages }}
      <li><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

The pages within each group will also be sorted by publish date, either ascending or descending depending on your grouping option. To sort the pages within each group, use one of the sorting methods. For example, to sort the pages within each group by title:

```go-html-template
{{ range .Pages.GroupByPublishDate "January 2006" }}
  <p>{{ .Key }}</p>
  <ul>
    {{ range .Pages.ByTitle }}
      <li><a href="{{ .RelPermalink }}">{{ .Title }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

## Layout string

{{% include "/_common/time-layout-string.md" %}}
