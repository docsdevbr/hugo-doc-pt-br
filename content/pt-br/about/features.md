---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/about/features.md
revision: c540e6d295880311a855308b1e14180cabbcd24a
status: ready

title: Recursos
description: |
  O rico e poderoso conjunto de recursos do Hugo fornece o framework e as
  ferramentas para criar sites estáticos que são construídos em segundos,
  geralmente menos.
categories: []
keywords: []
weight: 20
---

## Framework

[Multiplataforma]
: Instale o único executável do Hugo no Linux, macOS, Windows e muito mais.

[Multilíngue]
: Localize seu projeto para cada idioma e região, incluindo traduções, imagens,
datas, moedas, números, porcentagens e sequência de codificação de caracteres.
O framework multilíngue do Hugo oferece suporte a configurações de host único e
múltiplos hosts.

[Formatos de saída]
: Renderize cada página do seu site para um ou mais formatos de saída, com
controle granular por tipo de página, seção e caminho.
Embora HTML seja o formato de saída padrão, você pode adicionar JSON, RSS, CSV e
muito mais.
Por exemplo, você pode criar uma API REST para acessar o conteúdo.

[Templates]
: Crie templates usando variáveis, funções e métodos para transformar seu
conteúdo, recursos e dados em uma página publicada.
Embora os templates HTML sejam os mais comuns, você pode criar templates para
qualquer formato de saída.

[Temas]
: Reduza o tempo e o custo de desenvolvimento usando um das centenas de temas
contribuídos pela comunidade Hugo.
Há temas disponíveis para sites corporativos, projetos de documentação,
portfólios de imagens, landing pages, blogs pessoais e profissionais,
currículos, CVs e muito mais.

[Módulos]
: Reduza o tempo e o custo de desenvolvimento criando ou importando combinações
empacotadas de archetypes, assets, conteúdo, dados, templates, tabelas de
tradução, arquivos estáticos ou definições de configuração.
Um módulo pode servir como base para um novo site ou para incrementar um site
existente.

[Privacidade]
: Configure seu site para ajudar a cumprir com os regulamentos regionais de
privacidade.

[Segurança]
: O modelo de segurança do Hugo é baseado na premissa de que as pessoas autoras
de templates e configurações são confiáveis, mas as pessoas autoras de conteúdo
não.
Este modelo permite a geração de saída HTML segura contra injeção de código.
Outras proteções impedem a conexão de volta à máquina de uma pessoa invasora
para acessar aplicações arbitrárias, limitam o acesso a variáveis de ambiente
específicas, impedem conexões com fontes de dados remotas arbitrárias e muito
mais.

## Criação de conteúdo

[Formatos de conteúdo]
: Crie seu conteúdo usando Markdown, HTML, AsciiDoc, Emacs Org Mode, Pandoc ou
reStructuredText.
Markdown é o formato de conteúdo padrão, em conformidade com as especificações
[CommonMark] e [GitHub Flavored Markdown].

[Atributos Markdown]
: Aplique atributos HTML como `class` e `id` a imagens Markdown e elementos de
bloco, incluindo citações de bloco, blocos de código isolados, títulos, réguas
horizontais, listas, parágrafos e tabelas.

[Extensões Markdown]
: Aproveite as extensões Markdown incorporadas para criar tabelas, listas de
definições, notas de rodapé, listas de tarefas, texto inserido, texto destacado,
subscritos, sobrescritos e muito mais.

[Hooks de renderização Markdown]
: Substitua a conversão de Markdown para HTML ao renderizar citações de bloco,
blocos de código isolados, títulos, imagens, links e tabelas.
Por exemplo, renderize cada imagem autônoma como um elemento `figure` HTML.

[Diagramas]
: Use blocos de código isolados e hooks de renderização Markdown para incluir
diagramas em seu conteúdo.

[Matemática]
: Inclua equações e expressões matemáticas em Markdown usando marcação LaTeX.

[Realce de sintaxe]
: Realce sintaticamente exemplos de código usando o realçador de sintaxe
incorporado do Hugo, habilitado por padrão para blocos de código isolados no
Markdown.
O realçador de sintaxe suporta centenas de linguagens de código e dezenas de
estilos.

[Shortcodes]
: Use os shortcodes incorporados do Hugo ou crie os seus próprios para
inserir conteúdo complexo.
Por exemplo, use shortcodes para incluir elementos de `audio` e `video`,
renderizar tabelas de fontes de dados locais ou remotas, inserir trechos de
código de outras páginas e muito mais.

## Gerenciamento de conteúdo

[Adaptadores de conteúdo]
: Crie adaptadores de conteúdo para adicionar conteúdo dinamicamente ao criar
seu site.
Por exemplo, use um adaptador de conteúdo para criar páginas a partir de uma
fonte de dados remota, como JSON, TOML, YAML ou XML.

[Taxonomias]
: Classifique o conteúdo para estabelecer relacionamentos lógicos simples ou
complexos entre as páginas.
Por exemplo, crie uma taxonomia de pessoas autoras e atribua um ou mais pessoas
autoras a cada página.
Entre outros usos, o sistema de taxonomia fornece um índice ponderado invertido
para renderizar uma lista de páginas relacionadas, ordenadas por relevância.

[Dados]
: Aumente seu conteúdo usando fontes de dados locais ou remotas, incluindo CSV,
JSON, TOML, YAML e XML.
Por exemplo, crie um shortcode para renderizar uma tabela HTML a partir de um
arquivo CSV remoto.

[Menus]
: Forneça acesso rápido ao conteúdo por meio do sistema de menu do Hugo,
configurado automaticamente, globalmente ou página por página.
O sistema de menu é um componente essencial da arquitetura multilíngue do Hugo.

[Gerenciamento de URLs]
: Sirva qualquer página a partir de qualquer caminho por meio de configuração
global ou página por página.

## Esteiras de assets

[Processamento de imagem]
: Converta, redimensione, corte, gire, ajuste cores, aplique filtros, sobreponha
texto e imagens e extraia dados EXIF.

[Empacotamento de JavaScript]
: Transpile TypeScript e JSX para JavaScript, agrupe, remova código morto,
minimize, crie mapas de origem e execute hashes SRI.

[Processamento Sass]
: Transpile Sass para CSS, agrupe, remova código morto, minimize, crie mapas de
origem, execute hashes SRI e integre com PostCSS.

[Processamento CSS do Tailwind]
: Compile classes utilitárias CSS do Tailwind em CSS padrão, agrupe, remova
código morto, otimize, minimize, execute hashes SRI e integre com PostCSS.

## Desempenho

[Cache]
: Reduza o tempo e o custo de construção renderizando um template parcial uma
vez e, em seguida, armazene o resultado em cache, globalmente ou dentro de um
determinado contexto.
Por exemplo, armazene em cache o resultado de uma esteira de assets para evitar
o reprocessamento em cada página renderizada.

[Segmentação]
: Reduza o tempo e o custo de construção particionando seus sites em segmentos.
Por exemplo, renderize a página inicial e a "seção de notícias" a cada hora e
renderize o site inteiro uma vez por semana.

[Minificação]
: Minimize HTML, CSS e JavaScript para reduzir o tamanho dos arquivos, o consumo
de largura de banda e o tempo de carregamento.

[Adaptadores de conteúdo]: /content-management/content-adapters/

[Atributos Markdown]: /content-management/markdown-attributes/

[Cache]: /functions/partials/includecached/

[CommonMark]: https://spec.commonmark.org/current/

[Dados]: /content-management/data-sources/

[Diagramas]: /content-management/diagrams/

[Empacotamento de JavaScript]: /functions/js/build/

[Extensões Markdown]: /configuration/markup/#extensions

[Formatos de conteúdo]: /content-management/formats/

[Formatos de saída]: /configuration/output-formats/

[Gerenciamento de URLs]: /content-management/urls/

[GitHub Flavored Markdown]: https://github.github.com/gfm/

[Hooks de renderização Markdown]: /render-hooks/introduction/

[Matemática]: /content-management/mathematics/

[Menus]: /content-management/menus/

[Minificação]: /configuration/minify/

[Módulos]: /hugo-modules/

[Multilíngue]: /content-management/multilingual/

[Multiplataforma]: /installation/

[Privacidade]: /configuration/privacy/

[Processamento CSS do Tailwind]: /functions/css/tailwindcss/

[Processamento de imagem]: /content-management/image-processing/

[Processamento Sass]: /functions/css/Sass/

[Realce de sintaxe]: /content-management/syntax-highlighting/

[Segmentação]: /configuration/segments/

[Segurança]: /about/security/

[Shortcodes]: /content-management/shortcodes/

[Taxonomias]: /content-management/taxonomies/

[Temas]: https://themes.gohugo.io/

[Templates]: /templates/introduction/
