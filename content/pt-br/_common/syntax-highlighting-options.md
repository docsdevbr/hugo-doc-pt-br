---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/syntax-highlighting-options.md
revision: c540e6d295880311a855308b1e14180cabbcd24a
status: ready

_comment: Do not remove front matter.
---

anchorLineNos
: (`bool`) Se deve renderizar cada número de linha como um elemento âncora HTML,
definindo o atributo `id` do elemento `span` circundante para o número da linha.
Irrelevante se `lineNos` for `false`.
O padrão é `false`.

codeFences
: (`bool`) Se deve destacar blocos de código isolados.
O padrão é `true`.

guessSyntax
: (`bool`) Se deve detectar automaticamente a linguagem se o argumento `LANG`
estiver em branco ou definido como uma linguagem para a qual não há um
[lexer](g) correspondente.
Retorna para um analisador léxico de texto simples se não for possível detectar
a linguagem automaticamente.
O padrão é `false`.

  > [!note]
  > O realçador de sintaxe Chroma inclui analisadores léxicos para
  > aproximadamente 250 linguagens, mas apenas 5 deles implementaram a detecção
  > automática de linguagem.

hl_Lines
: (`string`) Uma lista delimitada por espaços de linhas para enfatizar dentro do
código destacado.
Para enfatizar as linhas 2, 3, 4 e 7, defina este valor como `2-4 7`.
Esta opção é independente da opção `lineNoStart`.

hl_inline
: (`bool`) Se deve renderizar o código destacado sem um contêiner de
encapsulamento.
O padrão é `false`.

lineAnchors
: (`string`) Ao renderizar um número de linha como um elemento âncora HTML,
adicione este valor ao atributo `id` do elemento `span` circundante.
Isso fornece atributos `id` exclusivos quando uma página contém dois ou mais
blocos de código.
Irrelevante se `lineNos` ou `anchorLineNos` for `false`.

lineNoStart
: (`int`) O número a ser exibido no início da primeira linha.
Irrelevante se `lineNos` for `false`.
O padrão é `1`.

lineNos
: (`any`) Controla a exibição do número da linha.
O padrão é `false`.
  - `true`: Habilita os números de linha, controlados por `lineNumbersInTable`.
  - `false`: Desabilita os números de linha.
  - `inline`: Habilita os números de linha em linha (define `lineNumbersInTable`
    como `false`).
  - `table`: Habilita os números de linha baseados em tabela (define
    `lineNumbersInTable` como `true`).

lineNumbersInTable
: (`bool`) Se deve renderizar o código destacado em uma tabela HTML com duas
células.
A célula de tabela à esquerda contém os números de linha, enquanto a célula de
tabela à direita contém o código.
Irrelevante se `lineNos` for `false`.
O padrão é `true`.

noClasses
: (`bool`) Se deve usar estilos CSS em linha em vez de um arquivo CSS externo.
O padrão é `true`.
Para usar um arquivo CSS externo, defina este valor como `false` e gere o
arquivo CSS a partir da linha de comando:

  ```text
  hugo gen chromastyles --style=monokai > syntax.css
  ```

style
: (`string`) Os estilos CSS a serem aplicados ao código ralçado.
Diferencia maiúsculas de minúsculas.
O padrão é `monokai`.
Veja [estilos de realce de sintaxe].

tabWidth
: (`int`) Substitua este número de espaços para cada caractere de tabulação no
seu código destacado.
Irrelevante se `noClasses` for `false`.
O padrão é `4`.

wrapperClass
: {{< new-in 0.140.2 />}}
: (`string`) A classe ou classes a serem usadas para o elemento mais externo do
código destacado.
O padrão é `highlight`.

[estilos de realce de sintaxe]: /quick-reference/syntax-highlighting-styles/
