---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: default sort order
---

The _default sort order_ for [_page collections_](g), used when no other criteria are set, follows this priority:

  1. [`weight`](/content-management/front-matter/#weight) (ascending)
  1. [`date`](/content-management/front-matter/#date) (descending)
  1. [`linkTitle`](/content-management/front-matter/#linktitle) falling back to [`title`](/content-management/front-matter/#title) (ascending)
  1. [logical path](g) (ascending)
