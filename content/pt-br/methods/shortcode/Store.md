---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Store
description: Returns a "scratch pad" to store and manipulate data, scoped to the current shortcode.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: maps.Scratch
    signatures: [SHORTCODE.Store]
---

{{< new-in 0.139.0 />}}

Use the `Store` method to create a [scratch pad](g) to store and manipulate data, scoped to the current shortcode. To create a scratch pad with a different [scope](g), refer to the [scope](#scope) section below.

> [!note]
> With the introduction of the [`newScratch`] function, and the ability to [assign values to template variables] after initialization, the `Store` method within a shortcode is mostly obsolete.

{{% include "_common/store-methods.md" %}}

{{% include "_common/scratch-pad-scope.md" %}}

[`newScratch`]: /functions/collections/newScratch/
[assign values to template variables]: https://go.dev/doc/go1.11#texttemplatepkgtexttemplate
