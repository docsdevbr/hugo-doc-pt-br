---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/ref-and-relref-error-handling.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Por padrão, o Hugo lançará um erro e falhará na construção se não puder resolver
o caminho.
Você pode alterar isso para um alerta na configuração do seu site e especificar
uma URL para retornar quando o caminho não puder ser resolvido.

{{< code-toggle file=hugo >}}
refLinksErrorLevel = 'warning'
refLinksNotFoundURL = '/alguma/outra/url'
{{< /code-toggle >}}
