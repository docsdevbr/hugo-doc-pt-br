---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/parsable-date-time-strings.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

 Formato                     | Fuso horário
:----------------------------|:----------------------
 `2023-10-15T13:18:50-07:00` | `America/Los_Angeles`
 `2023-10-15T13:18:50-0700`  | `America/Los_Angeles`
 `2023-10-15T13:18:50Z`      | `Etc/UTC`
 `2023-10-15T13:18:50`       | O padrão é `Etc/UTC`
 `2023-10-15`                | O padrão é `Etc/UTC`
 `15 Oct 2023`               | O padrão é `Etc/UTC`

Os três últimos exemplos não são totalmente qualificados e usam como padrão o
fuso horário `Etc/UTC`.
