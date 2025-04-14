---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/methods/taxonomy/get-a-taxonomy-object.md
revision: fd628be6ed3f1150d0030ba1424cc8f2da72efbb
status: ready

_comment: Do not remove front matter.
---

Antes de podermos usar um método `Taxonomy`, precisamos capturar um objeto
`Taxonomy`.

## Capture um objeto `Taxonomy`

Considere esta configuração do site:

{{< code-toggle file=hugo >}}
[taxonomies]
genero = 'generos'
pessoa autora = 'pessoas autoras'
{{< /code-toggle >}}

E esta estrutura de conteúdo:

```text
content/
├── livros/
│   ├── e-nao-sobrou-nenhum.md   --> generos: suspense
│   ├── morte-no-nilo.md         --> generos: suspense
│   ├── a-pousada-da-jamaica.md  --> generos: suspense, romance
│   └── orgulho-e-preconceito.md --> generos: romance
└── _index.md
```

Para capturar o objeto `Taxonomy` "generos" de qualquer template, use o método
[`Taxonomies`] em um objeto `Site`.

```go-html-template
{{ $taxonomyObject := .Site.Taxonomies.generos }}
```

Para capturar o objeto `Taxonomy` "generos" ao renderizar sua página com um
template de taxonomia, use o método [`Terms`] no objeto [`Data`] da página:

```go-html-template {file="layouts/_default/taxonomy.html"}
{{ $taxonomyObject := .Data.Terms }}
```

Para inspecionar a estrutura de dados:

```go-html-template
<pre>{{ debug.Dump $taxonomyObject }}</pre>
```

Embora os métodos [`Alphabetical`] e [`ByCount`] forneçam uma estrutura de dados
melhor para percorrer a taxonomia, você pode renderizar as páginas ponderadas
por termo diretamente do objeto `Taxonomy`:

```go-html-template
{{ range $term, $weightedPages := $taxonomyObject }}
  <h2><a href="{{ .Page.RelPermalink }}">{{ .Page.LinkTitle }}</a></h2>
  <ul>
    {{ range $weightedPages }}
      <li><a href="{{ .RelPermalink }}">{{ .LinkTitle }}</a></li>
    {{ end }}
  </ul>
{{ end }}
```

No exemplo acima, o primeiro elemento âncora é um link para a página do termo.

[`Alphabetical`]: /methods/taxonomy/alphabetical/

[`ByCount`]: /methods/taxonomy/bycount/

[`data`]: /methods/page/data/

[`taxonomies`]: /methods/site/taxonomies/

[`terms`]: /methods/page/data/#in-a-taxonomy-template
