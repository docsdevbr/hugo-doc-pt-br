---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/methods/pages/next-and-prev.md
revision: fd628be6ed3f1150d0030ba1424cc8f2da72efbb
status: ready

_comment: Do not remove front matter.
---

O Hugo determina a _próxima_ página e a página _anterior_ ordenando o conjunto
de páginas de acordo com esta hierarquia de ordenação:

 Campo         | Precedência | Direção de ordenação
:--------------|:------------|:--------------------
 [`weight`]    | 1           | decrescente
 [`date`]      | 2           | decrescente
 [`linkTitle`] | 3           | decrescente
 [`path`]      | 4           | decrescente

[`date`]: /methods/page/date/

[`linkTitle`]: /methods/page/linktitle/

[`path`]: /methods/page/path/

[`weight`]: /methods/page/weight/

O conjunto de páginas ordenadas usado para determinar a _próxima_ página e a
página _anterior_ é independente de outros conjuntos de páginas, o que pode
levar a comportamentos inesperados.

Por exemplo, com esta estrutura de conteúdo:

```text
content/
├── paginas/
│   ├── _index.md
│   ├── pagina-1.md   <-- front matter: weight = 10
│   ├── pagina-2.md   <-- front matter: weight = 20
│   └── pagina-3.md   <-- front matter: weight = 30
└── _index.md
```

E estes templates:

```go-html-template {file="layouts/_default/list.html"}
{{ range .Pages.ByWeight }}
  <h2><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></h2>
{{ end }}
```

```go-html-template {file="layouts/_default/single.html"}
{{ $pages := .CurrentSection.Pages.ByWeight }}

{{ with $pages.Prev . }}
  <a href="{{ .RelPermalink }}">Anterior</a>
{{ end }}

{{ with $pages.Next . }}
  <a href="{{ .RelPermalink }}">Próxima</a>
{{ end }}
```

Ao visitar a pagina-2:

- O método `Prev` aponta para pagina-3
- O método `Next` aponta para pagina-1

Para inverter o significado de _próxima_ página e página _anterior_, você pode
encadear o método [`Reverse`] à definição da coleção de páginas:

```go-html-template {file="layouts/_default/single.html"}
{{ $pages := .CurrentSection.Pages.ByWeight.Reverse }}

{{ with $pages.Prev . }}
  <a href="{{ .RelPermalink }}">Anterior</a>
{{ end }}

{{ with $pages.Next . }}
  <a href="{{ .RelPermalink }}">Próxima</a>
{{ end }}
```

[`Reverse`]: /methods/pages/reverse/
