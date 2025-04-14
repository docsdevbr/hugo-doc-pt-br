---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/menu-entries/pre-and-post.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Nesta configuração de site, habilitamos a renderização de [shortcodes de emojis]
e adicionamos shortcodes de emojis antes (pré) e depois (pós) de cada entrada do
menu:

{{< code-toggle file=hugo >}}
enableEmoji = true

[[menus.main]]
name = 'Sobre'
pageRef = '/sobre'
post = ':point_left:'
pre = ':point_right:'
weight = 10

[[menus.main]]
name = 'Contato'
pageRef = '/contato'
post = ':arrow_left:'
pre = ':arrow_right:'
weight = 20
{{< /code-toggle >}}

Para renderizar o menu:

```go-html-template
<ul>
  {{ range .Site.Menus.main }}
    <li>
      {{ .Pre | markdownify }}
      <a href="{{ .URL }}">{{ .Name }}</a>
      {{ .Post | markdownify }}
    </li>
  {{ end }}
</ul>
```

[shortcodes de emojis]: /quick-reference/emojis/
