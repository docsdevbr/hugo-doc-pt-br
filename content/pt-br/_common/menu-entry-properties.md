---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/menu-entry-properties.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

<!--
This description list intentionally excludes the `pageRef` and `url` properties. Add those properties manually after using the include shortcode to include this list.
-->

identifier
: (`string`) Obrigatório quando duas ou mais entradas de menu têm o mesmo `name`
(nome), ou ao localizar o `name` usando tabelas de tradução.
Deve começar com uma letra, seguida por letras, dígitos ou sublinhados.

name
: (`string`) O texto a ser exibido ao renderizar a entrada de menu.

params
: (`map`) Propriedades definidas pela pessoa usuária para a entrada de menu.

parent
: (`string`) O `identifier` (identificador) da entrada de menu pai.
Se o identificador não for definido, use `name`.
Obrigatório para entradas filhas em um menu aninhado.

post
: (`string`) O HTML a ser anexado ao renderizar a entrada de menu.

pre
: (`string`) O HTML a ser prefixado ao renderizar a entrada de menu.

title
: (`string`) O atributo `title` HTML da entrada de menu renderizada.

weight
: (`int`) Um inteiro diferente de zero que indica a posição da entrada em
relação à raiz do menu, ou ao seu pai para uma entrada filha.
Entradas mais leves flutuam para o topo, enquanto entradas mais pesadas afundam
para a base.
