---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/getting-started/quick-start.md
revision: c540e6d295880311a855308b1e14180cabbcd24a
status: ready

title: Início rápido
description: Crie um site Hugo em minutos.
categories: []
keywords: []
params:
  minVersion: v0.128.0
weight: 10
aliases: [/quickstart/,/overview/quickstart/]
---

Neste tutorial você irá:

1. Criar um site
1. Adicionar conteúdo
1. Configurar o site
1. Publicar o site

## Pré-requisitos

Antes de começar este tutorial, você deve:

1. [Instalar o Hugo] (edição estendida ou estendida/de implantação,
   {{% param "minVersion" %}} ou posterior)
1. [Instalar o Git]

Você também deve estar confortável trabalhando na linha de comando.

## Crie um site

### Comandos

> [!note]
> **Se você for uma pessoa usuária do Windows:**
>
> - Não use o Prompt de Comando
> - Não use o Windows PowerShell
> - Execute estes comandos do [PowerShell] ou de um terminal Linux, como WSL ou Git > Bash
>
> PowerShell e Windows PowerShell [são aplicações diferentes].

Verifique se você instalou o Hugo {{% param "minVersion" %}} ou posterior.

```text
hugo version
```

Execute estes comandos para criar um site Hugo com o tema [Ananke].
A próxima seção fornece uma explicação de cada comando.

```text
hugo new site inicio-rapido
cd inicio-rapido
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

Acesse seu site usando a URL exibida em seu terminal.
Pressione `Ctrl + C` para parar o servidor de desenvolvimento do Hugo.

### Explicação dos comandos

Criar a [estrutura de diretório] para seu projeto no diretório `inicio-rapido`.

```text
hugo new site inicio-rapido
```

Alterar o diretório atual para a raiz do seu projeto.

```text
cd inicio-rapido
```

Inicializar um repositório Git vazio no diretório atual.

```text
git init
```

Clonar o tema [Ananke] no diretório `themes`, adicionando-o ao seu projeto como
um [submódulo Git].

```text
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

Acrescentar uma linha ao arquivo de configuração do site, indicando o tema
atual.

```text
echo "theme = 'ananke'" >> hugo.toml
```

Iniciar o servidor de desenvolvimento do Hugo para visualizar o site.

```text
hugo server
```

Pressione `Ctrl + C` para parar o servidor de desenvolvimento do Hugo.

## Adicione conteúdo

Adicione uma nova página ao seu site.

```text
hugo new content content/posts/meu-primeiro-post.md
```

O Hugo criou o arquivo no diretório `content/posts`.
Abra o arquivo com seu editor.

```text
+++
title = 'Meu primeiro post'
date = 2024-01-14T07:07:07+01:00
draft = true
+++
```

Observe que o valor `draft` (rascunho) na [front matter] é `true`.
Por padrão, o Hugo não publica conteúdo de rascunho quando você cria o site.
Saiba mais sobre [conteúdo de rascunho, futuro e expirado].

Adicione um pouco de [Markdown] ao corpo do post, mas não altere o valor de
`draft`.

```text
+++
title = 'Meu primeiro post'
date = 2024-01-14T07:07:07+01:00
draft = true
+++
## Introdução

Este é um texto em **negrito** e este é um texto em *ênfase*.

Visite o site do [Hugo](https://gohugo.io)!
```

Salve o arquivo e inicie o servidor de desenvolvimento do Hugo para visualizar o
site.
Você pode executar qualquer um dos seguintes comandos para incluir conteúdo de
rascunho.

```text
hugo server --buildDrafts
hugo server -D
```

Acesse seu site usando a URL exibida em seu terminal.
Mantenha o servidor de desenvolvimento em execução enquanto você continua
adicionando e alterando conteúdo.

Quando estiver contente com seu novo conteúdo, defina o parâmetro de _front
matter_ `draft` como `false`.

> [!note]
> O mecanismo de renderização do Hugo está em conformidade com a [especificação]
> CommonMark para Markdown.
> A organização CommonMark fornece uma [ferramenta útil de teste ao vivo]
> alimentada pela implementação de referência.

## Configure o site

Com seu editor, abra o arquivo de [configuração do site] (`hugo.toml`) na raiz
do seu projeto.

```text
baseURL = 'https://example.org/'
languageCode = 'pt-br'
title = 'Meu novo site Hugo'
theme = 'ananke'
```

Faça as seguintes alterações:

1. Defina a `baseURL` (URL base) para seu site de produção.
   Este valor deve começar com o protocolo e terminar com uma barra, conforme
   mostrado acima.
1. Defina o `languageCode` (código de idioma) para seu idioma e região.
1. Defina o `title` (título) para seu site de produção.

Inicie o servidor de desenvolvimento do Hugo para verificar suas alterações,
lembrando-se de incluir o conteúdo do rascunho.

```text
hugo server -D
```

> [!note]
> A maioria das pessoas autoras de temas fornece diretrizes e opções de
> configuração.
> Certifique-se de visitar o repositório do seu tema ou o site da documentação
> para obter detalhes.
>
> As pessoas da [New Dynamic], autoras do tema Ananke, fornecem [documentação]
> para configuração e uso.
> Elas também fornecem um [site de demonstração].

## Publique o site

Nesta etapa, você _publicará_ seu site, mas não o _implantará_.

Quando você _publica_ seu site, o Hugo cria todo o site estático no
diretório `public` na raiz do seu projeto.
Isso inclui os arquivos HTML e assets como imagens, arquivos CSS e arquivos
JavaScript.

Quando você publica seu site, normalmente _não_ deseja incluir
[conteúdo de rascunho, futuro ou expirado].
O comando é simples.

```text
hugo
```

Para aprender como _implantar_ seu site, consulte a seção
[hospedagem e implantação].

## Peça ajuda

O [fórum] do Hugo é uma comunidade ativa de pessoas usuárias e desenvolvedoras
que respondem a perguntas, compartilham conhecimento e fornecem exemplos.
Uma busca rápida em mais de 20.000 tópicos geralmente responderá à sua pergunta.
Certifique-se de ler sobre [como solicitar ajuda] antes de fazer sua primeira
pergunta.

## Outros recursos

Para outros recursos para ajudar você a aprender sobre o Hugo, incluindo livros
e tutoriais em vídeo, consulte a página de
[recursos de aprendizagem externos](/getting-started/external-learning-resources/).

[A New Dynamic]: https://www.thenewdynamic.com/

[Ananke]: https://github.com/theNewDynamic/gohugo-theme-ananke

[como solicitar ajuda]: https://discourse.gohugo.io/t/requesting-help/9132

[configuração do site]: /configuration/

[conteúdo de rascunho, futuro e expirado]: /getting-started/usage/#conteudo-de-rascunho-futuro-e-expirado

[conteúdo de rascunho, futuro ou expirado]: /getting-started/usage/#conteudo-de-rascunho-futuro-e-expirado

[documentação]: https://github.com/theNewDynamic/gohugo-theme-ananke#readme

[especificação]: https://spec.commonmark.org/

[estrutura de diretório]: /getting-started/directory-structure/

[ferramenta útil de teste ao vivo]: https://spec.commonmark.org/dingus/

[fórum]: https://discourse.gohugo.io/

[front matter]: /content-management/front-matter/

[hospedagem e implantação]: /host-and-deploy/

[Instalar o Git]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

[Instalar o Hugo]: /installation/

[Markdown]: https://daringfireball.net/projects/markdown

[PowerShell]: https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows

[são aplicações diferentes]: https://learn.microsoft.com/en-us/powershell/scripting/whats-new/differences-from-windows-powershell?view=powershell-7.3

[site de demonstração]: https://gohugo-ananke-theme-demo.netlify.app/

[submódulo Git]: https://git-scm.com/book/en/v2/Git-Tools-Submodules
