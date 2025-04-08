---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/functions/truthy-falsy.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Os valores falsos são `false`, `0`, qualquer ponteiro `nil` ou valor de
interface, qualquer array, slice, map ou string de comprimento zero e valores
`time.Time` zero.

Todo o resto é verdadeiro.
