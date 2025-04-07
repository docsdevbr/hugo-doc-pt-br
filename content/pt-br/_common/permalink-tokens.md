---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/permalink-tokens.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

`:year`
: O ano de 4 dígitos conforme definido no campo `date` da front matter.

`:month`
: O mês de 2 dígitos conforme definido no campo `date` da front matter.

`:monthname`
: O nome do mês conforme definido no campo `date` da front matter.

`:day`
: O dia de 2 dígitos conforme definido no campo `date` da front matter.

`:weekday`
: O dia da semana de 1 dígito conforme definido no campo `date` da front matter
(domingo = `0`).

`:weekdayname`
: O nome do dia da semana conforme definido no campo `date` da front matter.

`:yearday`
: O dia do ano de 1 a 3 dígitos conforme definido no campo `date` da front
matter.

`:section`
: A seção do conteúdo.

`:sections`
: A hierarquia das seções do conteúdo.
Você pode usar uma seleção das seções usando a _sintaxe de fatia_:
`:sections[1:]` inclui todas, exceto a primeira, `:sections[:last]` inclui
todas, exceto a última, `:sections[last]` inclui apenas a última,
`:sections[1:2]` inclui as seções 2 e 3.
Observe que esse acesso de fatia não lançará erros do tipo fora dos limites,
então você não precisa ser exato.

`:title`
: O `title` conforme definido na front matter, senão o título automático.
O Hugo gera títulos automaticamente para páginas de seção, taxonomia e termo que
não são apoiadas por um arquivo.

`:slug`
: O `slug` conforme definido na front matter, senão o título conforme definido
na front matter, senão o título automático.
O Hugo gera títulos automaticamente para páginas de seção, taxonomia e termo que
não são apoiadas por um arquivo.

`:filename`
: O nome do arquivo de conteúdo sem extensão, aplicável ao tipo de página
`page`.

  {{< deprecated-in v0.144.0 >}}
  O token `:filename` foi descontinuado.
  Use `:contentbasename` em vez disso.
  {{< /deprecated-in >}}

`:slugorfilename`
: O `slug` conforme definido na front matter, senão o nome do arquivo de
conteúdo sem extensão, aplicável ao tipo de página `page`.

  {{< deprecated-in v0.144.0 >}}
  O token `:slugorfilename` foi descontinuado.
  Use `:slugorcontentbasename` em vez disso.
  {{< /deprecated-in >}}

`:contentbasename`
: {{< new-in 0.144.0 />}}
: O [nome base do conteúdo].

`:slugorcontentbasename`
: {{< new-in 0.144.0 />}}
: O `slug` conforme definido na front matter, senão o [nome base do conteúdo].

Para valores relacionados ao tempo, você também pode usar os componentes de
string de layout definidos no [pacote time] do Go.
Por exemplo:

{{< code-toggle file=hugo >}}
permalinks:
  posts: /:06/:1/:2/:title/
{{< /code-toggle >}}

[nome base do conteúdo]: /methods/page/file/#contentbasename

[pacote time]: https://pkg.go.dev/time#pkg-constants
