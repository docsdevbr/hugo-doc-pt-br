---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: ordered taxonomy
---

Created by invoking the [`Alphabetical`](/methods/taxonomy/alphabetical/) or [`ByCount`](/methods/taxonomy/bycount/) method on a [`Taxonomy`](g) object, which is a [_map_](g), an _ordered taxonomy_ is a [_slice_](g), where each element is an object that contains the [_term_](g) and a slice of its [_weighted pages_](g).
