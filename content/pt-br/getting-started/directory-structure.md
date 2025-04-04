---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/getting-started/directory-structure.md
revision: c540e6d295880311a855308b1e14180cabbcd24a
status: ready

title: Estrutura de diretório
description: Uma visão geral da estrutura de diretório do Hugo.
categories: []
keywords: []
weight: 30
aliases: [/overview/source-directory/]
---

Cada projeto Hugo é um diretório, com subdiretórios que contribuem para o
conteúdo, estrutura, comportamento e apresentação do seu site.

## Esqueleto do site

O Hugo gera um esqueleto de projeto quando você cria um novo site.
Por exemplo, este comando:

```sh
hugo new site meu-site
```

Cria esta estrutura de diretório:

```txt
meu-site/
├── archetypes/
│   └── default.md
├── assets/
├── content/
├── data/
├── i18n/
├── layouts/
├── static/
├── themes/
└── hugo.toml         <-- configuração do site
```

Dependendo dos requisitos, você pode querer organizar a configuração do seu site
em subdiretórios:

```txt
meu-site/
├── archetypes/
│   └── default.md
├── assets/
├── config/           <-- configuração do site
│   └── _default/
│       └── hugo.toml
├── content/
├── data/
├── i18n/
├── layouts/
├── static/
└── themes/
```

Quando você cria seu site, o Hugo cria um diretório `public` e, normalmente, um
diretório `resources` também:

```txt
meu-site/
├── archetypes/
│   └── default.md
├── assets/
├── config/       
│   └── _default/
│       └── hugo.toml
├── content/
├── data/
├── i18n/
├── layouts/
├── public/       <-- criado quando você constrói seu site
├── resources/    <-- criado quando você constrói seu site
├── static/
└── themes/
```

## Diretórios

Cada um dos subdiretórios contribui para o conteúdo, estrutura, comportamento ou
apresentação do seu site.

archetypes
: O diretório `archetypes` contém templates para novos conteúdos.
Consulte os [detalhes](/content-management/archetypes/).

assets
: O diretório `assets` contém recursos globais que normalmente passaram por uma
esteira de assets.
Isso inclui recursos como imagens, CSS, Sass, JavaScript e TypeScript.
Consulte os [detalhes](/hugo-pipes/introduction/).

config
: O diretório `config` contém a configuração do seu site, possivelmente dividida
em vários subdiretórios e arquivos.
Para projetos com configuração mínima ou projetos que não precisam se comportar
de forma diferente em ambientes diferentes, um único arquivo de configuração
chamado `hugo.toml` na raiz do projeto é suficiente.
Consulte os [detalhes](/configuration/introduction/#configuration-directory).

content
: O diretório `content` contém os arquivos de marcação (normalmente Markdown) e
recursos de página que compõem o conteúdo do seu site.
Consulte os [detalhes](/content-management/organization/).

data
: O diretório `data` contém arquivos de dados (JSON, TOML, YAML ou XML) que
incrementam o conteúdo, a configuração, a localização e a navegação.
Consulte os [detalhes](/content-management/data-sources/).

i18n
: O diretório `i18n` contém tabelas de tradução para sites multilíngues.
Consulte os [detalhes](/content-management/multilingual/).

layouts
: O diretório `layouts` contém templates para transformar conteúdo, dados e
recursos em um site completo.
Consulte os [detalhes](/templates/).

public
: O diretório `public` contém o site publicado, gerado quando você executa os
comandos `hugo` ou `hugo server`.
O Hugo recria esse diretório e seu conteúdo conforme necessário.
Consulte os [detalhes](/getting-started/usage/#construa-seu-site).

resources
: O diretório `resources` contém a saída em cache das esteiras de assets do
Hugo, gerada quando você executa os comandos `hugo` ou `hugo server`.
Por padrão, esse diretório de cache inclui CSS e imagens.
O Hugo recria esse diretório e seu conteúdo conforme necessário.

static
: O diretório `static` contém arquivos que serão copiados para o diretório
`public` quando você criar seu site.
Por exemplo: `favicon.ico`, `robots.txt` e arquivos que verificam a propriedade
do site.
Antes da introdução de [page bundles](g) e
[esteiras de assets](/hugo-pipes/introduction/), o diretório `static` também era
usado para imagens, CSS e JavaScript.

themes
: O diretório `themes` contém um ou mais [themes](g), cada um em seu próprio
subdiretório.

## Sistema de arquivos de união

O Hugo cria um sistema de arquivos de união, permitindo que você monte dois ou
mais diretórios no mesmo local.
Por exemplo, digamos que seu diretório home contém um projeto Hugo em um
diretório e conteúdo compartilhado em outro:

```text
home/
└── user/
    ├── meu-site/
    │   ├── content/
    │   │   ├── livros/
    │   │   │   ├── _index.md
    │   │   │   ├── livro-1.md
    │   │   │   └── livro-2.md
    │   │   └── _index.md
    │   ├── themes/
    │   │   └── meu-tema/
    │   └── hugo.toml
    └── shared-content/
        └── filmes/
            ├── _index.md
            ├── filme-1.md
            └── filme-2.md
```

Você pode incluir o conteúdo compartilhado ao construir seu site usando
montagens.
Na configuração do seu site:

{{< code-toggle file=hugo >}}
[[module.mounts]]
source = 'content'
target = 'content'

[[module.mounts]]
source = '/home/user/shared-content'
target = 'content'
{{< /code-toggle >}}

> [!note]
> Quando você sobrepõe um diretório sobre outro, você deve montar ambos os
> diretórios.
>
> O Hugo não segue links simbólicos.
> Se você precisa da funcionalidade fornecida pelos links simbólicos, use o
> sistema de arquivos de união do Hugo.

Após a montagem, o sistema de arquivos de união tem esta estrutura:

```text
home/
└── user/
    └── meu-site/
        ├── content/
        │   ├── livros/
        │   │   ├── _index.md
        │   │   ├── livro-1.md
        │   │   └── livro-2.md
        │   ├── filmes/
        │   │   ├── _index.md
        │   │   ├── filme-1.md
        │   │   └── filme-2.md
        │   └── _index.md
        ├── themes/
        │   └── meu-tema/
        └── hugo.toml
```

> [!note]
> Quando dois ou mais arquivos têm o mesmo caminho, a ordem de precedência segue
> a ordem das montagens.
> Por exemplo, se o diretório de conteúdo compartilhado contiver
> `livros/livro-1.md`, ele será ignorado porque o diretório de conteúdo do
> projeto foi montado primeiro.

Você pode montar diretórios para `archetypes`, `assets`, `content`, `data`,
`i18n`, `layouts` e `static`.
Consulte os [detalhes](/configuration/module/#mounts).

Você também pode montar diretórios de repositórios Git usando Módulos Hugo.
Consulte os [detalhes](/hugo-modules/).

## Esqueleto do tema

O Hugo gera um esqueleto de tema funcional quando você cria um novo tema.
Por exemplo, este comando:

```text
hugo new theme meu-tema
```

Cria esta estrutura de diretório (subdiretórios não mostrados):

```text
meu-tema/
├── archetypes/
├── assets/
├── content/
├── data/
├── i18n/
├── layouts/
├── static/
├── LICENSE
├── README.md
├── hugo.toml
└── theme.toml
```

Usando o sistema de arquivos de união descrito acima, o Hugo monta cada um
desses diretórios no local correspondente no projeto.
Quando dois arquivos têm o mesmo caminho, o arquivo no diretório do projeto tem
precedência.
Isso permite que você, por exemplo, substitua o template de um tema colocando
uma cópia no mesmo local dentro do diretório do projeto.

Se você estiver usando simultaneamente componentes de dois ou mais temas ou
módulos, e houver uma colisão de caminho, a primeira montagem tem precedência.
