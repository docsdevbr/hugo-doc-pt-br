---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/glob-patterns.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

 Caminho            | Padrão             | Correspondência
:-------------------|:-------------------|:----------------
 `images/foo/a.jpg` | `images/foo/*.jpg` | `true`
 `images/foo/a.jpg` | `images/foo/*.*`   | `true`
 `images/foo/a.jpg` | `images/foo/*`     | `true`
 `images/foo/a.jpg` | `images/*/*.jpg`   | `true`
 `images/foo/a.jpg` | `images/*/*.*`     | `true`
 `images/foo/a.jpg` | `images/*/*`       | `true`
 `images/foo/a.jpg` | `*/*/*.jpg`        | `true`
 `images/foo/a.jpg` | `*/*/*.*`          | `true`
 `images/foo/a.jpg` | `*/*/*`            | `true`
 `images/foo/a.jpg` | `**/*.jpg`         | `true`
 `images/foo/a.jpg` | `**/*.*`           | `true`
 `images/foo/a.jpg` | `**/*`             | `true`
 `images/foo/a.jpg` | `**`               | `true`
 `images/foo/a.jpg` | `*/*.jpg`          | `false`
 `images/foo/a.jpg` | `*.jpg`            | `false`
 `images/foo/a.jpg` | `*.*`              | `false`
 `images/foo/a.jpg` | `*`                | `false`
