---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/functions/regular-expressions.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Ao especificar a expressão regular, use uma [string literal] bruta (crases) em
vez de uma string literal interpretada (aspas duplas) para simplificar a
sintaxe.
Com uma string literal interpretada, você deve escapar barras invertidas.

O pacote de expressão regular do Go implementa a [sintaxe RE2].
A sintaxe RE2 é um subconjunto daquela aceita pela [PCRE], falando grosso modo,
e com várias [ressalvas].
Observe que a sequência de escape `\C` RE2 não é suportada.

[PCRE]: https://www.pcre.org/

[ressalvas]: https://swtch.com/~rsc/regexp/regexp3.html#caveats

[sintaxe RE2]: https://github.com/google/re2/wiki/Syntax/

[string literal]: https://go.dev/ref/spec#String_literals
