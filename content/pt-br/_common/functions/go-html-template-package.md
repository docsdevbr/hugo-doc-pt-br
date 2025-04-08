---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/functions/go-html-template-package.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

O Hugo usa os pacotes [text/template] e [html/template] do Go.

O pacote text/template implementa templates orientados a dados para gerar saída
textual, enquanto o pacote html/template implementa templates orientados a dados
para gerar saída HTML segura contra injeção de código.

Por padrão, o Hugo usa o pacote html/template ao renderizar arquivos HTML.

Para gerar saída HTML segura contra injeção de código, o pacote html/template
escapa strings em certos contextos.

[html/template]: https://pkg.go.dev/html/template

[text/template]: https://pkg.go.dev/text/template
