---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/methods/page/output-format-methods.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

### Get IDENTIFICADOR

(`any`) Retorna o objeto `OutputFormat` com o identificador fornecido.

### MediaType

(`media.Type`) Retorna o tipo de mídia do formato de saída.

### MediaType.MainType

(`string`) Retorna o tipo principal do tipo de mídia do formato de saída.

### MediaType.SubType

(`string`) Retorna o subtipo do tipo de mídia do formato atual.

### Name

(`string`) Retorna o identificador de saída do formato de saída.

### Permalink

(`string`) Retorna o link permanente da página gerada pelo formato de saída
atual.

### Rel

(`string`) Retorna o valor `rel` do formato de saída, seja o padrão ou conforme
definido na configuração do site.

### RelPermalink

(`string`) Retorna o link permanente relativo da página gerada pelo formato de
saída atual.
