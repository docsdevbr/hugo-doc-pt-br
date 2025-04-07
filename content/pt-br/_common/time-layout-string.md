---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/time-layout-string.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

Formata um valor `time.Time` com base no [tempo de referência do Go]:

[tempo de referência do Go]: https://pkg.go.dev/time#pkg-constants

```text
Mon Jan 2 15:04:05 MST 2006
```

Crie uma string de layout usando estes componentes:

 Descrição                     | Componentes válidos
:------------------------------|:-----------------------------------------------
 Ano                           | `"2006" "06"`
 Mês                           | `"Jan" "January" "01" "1"`
 Dia da semana                 | `"Mon" "Monday"`
 Dia do mês                    | `"2" "_2" "02"`
 Dia do ano                    | `"__2" "002"`
 Hora                          | `"15" "3" "03"`
 Minuto                        | `"4" "04"`
 Segundo                       | `"5" "05"`
 Período AM/PM                 | `"PM"`
 Deslocamentos de fuso horário | `"-0700" "-07:00" "-07" "-070000" "-07:00:00"`

Substitua o sinal na string de layout por um Z para imprimir Z em vez de um
deslocamento para o fuso UTC.

 Descrição                     | Componentes válidos
:------------------------------|:-----------------------------------------------
 Deslocamentos de fuso horário | `"Z0700" "Z07:00" "Z07" "Z070000" "Z07:00:00"`

```go-html-template
{{ $t := "2023-01-27T23:44:58-08:00" }}
{{ $t = time.AsTime $t }}
{{ $t = $t.Format "Jan 02, 2006 3:04 PM Z07:00" }}

{{ $t }} → Jan 27, 2023 11:44 PM -08:00
```

Strings como `PST` e `CET` não são fusos horários.
São _abreviações_ de fuso horário.

Strings como `-07:00` e `+01:00` não são fusos horários.
São _deslocamentos_ de fuso horário.

Um fuso horário é uma área geográfica com o mesmo horário local.
Por exemplo, o fuso horário abreviado por `PST` e `PDT` (dependendo do horário
de verão) é `America/Los_Angeles`.
