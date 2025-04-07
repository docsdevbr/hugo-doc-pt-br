---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/scratch-pad-scope.md
revision: 6a7fd42ff739686d112ce9b13f9141952cdea556
status: ready

_comment: Do not remove front matter.
---

## Escopo

O método ou função usado para criar um bloco de rascunho determina seu escopo.
Por exemplo, use o método `Store` em um objeto `Page` para criar um bloco de
rascunho com escopo na página.

 Escopo    | Método ou função
:----------|:------------------------
 página    | [`PAGE.Store`]
 site      | [`SITE.Store`]
 global    | [`hugo.Store`]
 local     | [`collections.NewScratch`]
 shortcode | [`SHORTCODE.Store`]

[`collections.newscratch`]: functions/collections/newscratch

[`hugo.store`]: /functions/hugo/store

[`page.store`]: /methods/page/store

[`site.store`]: /methods/site/store

[`shortcode.store`]: /methods/shortcode/store
