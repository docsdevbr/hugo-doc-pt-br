---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/methods/taxonomy/ordered-taxonomy-element-methods.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Uma taxonomia ordenada é um slice, onde cada elemento é um objeto que contém o
termo e um slice de suas páginas ponderadas.

Cada elemento do slice fornece os seguintes métodos:

Count
: (`int`) Retorna o número de páginas às quais o termo está atribuído.

Page
: (`page.Page`) Retorna o objeto `Page` do termo, útil para vincular à página do
termo.

Pages
: (`page.Pages`) Retorna um objeto `Pages` contendo os objetos `Page` aos quais
o termo está atribuído, ordenados por [taxonomic weight](g).
Para ordenar ou agrupar, use qualquer um dos [métodos] disponíveis para o objeto
`Pages`.
Por exemplo, ordene pela data da última modificação.

Term
: (`string`) Retorna o nome do termo.

WeightedPages
: (`page.WeightedPages`) Retorna um slice de páginas ponderadas às quais o termo
está atribuído, ordenadas por peso taxonômico.
O método `Pages` acima é mais flexível, permitindo ordenar e agrupar.

[métodos]: /methods/pages/
