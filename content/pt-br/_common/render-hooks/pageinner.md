---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/render-hooks/pageinner.md
revision: c540e6d295880311a855308b1e14180cabbcd24a
status: ready

_comment: Do not remove front matter.
---

## Detalhes de `PageInner`

{{< new-in 0.125.0 />}}

O principal caso de uso de `PageInner` é resolver links e [page resources](g)
relativos a uma `Page` incluída.
Por exemplo, crie um shortcode "include" para compor uma página a partir de
vários arquivos de conteúdo, preservando um contexto global para notas de rodapé
e o sumário:

```go-html-template {file="layouts/shortcodes/include.html" copy=true}
{{ with .Get 0 }}
  {{ with $.Page.GetPage . }}
    {{- .RenderShortcodes }}
  {{ else }}
    {{ errorf "O shortcode %q não conseguiu encontrar %q. Consulte %s" $.Name . $.Position }}
  {{ end }}
{{ else }}
  {{ errorf "O shortcode %q requer um parâmetro posicional que indique o caminho lógico do arquivo a ser incluído. Consulte %s" .Name .Position }}
{{ end }}
```

Em seguida, chame o shortcode no seu Markdown:

```text {file="content/posts/p1.md"}
{{%/* include "/posts/p2" */%}}
```

Qualquer hook de renderização acionado durante a renderização de `/posts/p2`
receberá:

- `/posts/p1` ao chamar `Page`
- `/posts/p2` ao chamar `PageInner`

`PageInner` retorna ao valor de `Page` se não for relevante e sempre retorna um
valor.

> [!note]
> O método `PageInner` é relevante apenas para shortcodes que invocam o método
> [`RenderShortcodes`], e você deve chamar o shortcode usando
> [notação Markdown].

Como exemplo prático, os hooks de renderização de link e imagem incorporados do
Hugo usam o método `PageInner` para resolver destinos de link e imagem em
Markdown.
Veja o código-fonte de cada um:

- [Hook de renderização de link incorporado]
- [Hook de renderização de imagem incorporada]

[`RenderShortcodes`]: /methods/page/rendershortcodes/

[notação Markdown]: /content-management/shortcodes/#notation

[Hook de renderização de link incorporado]: {{% eturl render-link %}}

[Hook de renderização de imagem incorporada]: {{% eturl render-image %}}
