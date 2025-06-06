---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Configure page
linkTitle: Page
description: Configure page behavior.
categories: []
keywords: []
---

{{< new-in 0.133.0 />}}

{{% glossary-term "default sort order" %}}

Hugo uses the default sort order to determine the _next_ and _previous_ page relative to the current page when calling these methods on a `Page` object:

- [`Next`](/methods/page/next/) and [`Prev`](/methods/page/prev/)
- [`NextInSection`](/methods/page/nextinsection/) and [`PrevInSection`](/methods/page/previnsection/)

This is based on this default site configuration:

{{< code-toggle config=page />}}

To reverse the meaning of _next_ and _previous_:

{{< code-toggle file=hugo >}}
[page]
  nextPrevInSectionSortOrder = 'asc'
  nextPrevSortOrder = 'asc'
{{< /code-toggle >}}

> [!note]
> These settings do not apply to the [`Next`] or [`Prev`] methods on a `Pages` object.

[`Next`]: /methods/pages/next
[`Prev`]: /methods/pages/next
