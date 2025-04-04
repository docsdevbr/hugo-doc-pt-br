---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/getting-started/usage.md
revision: f26ca047a567980ffec8a62e2feade06d143426f
status: ready

title: Uso básico
description: |
  Use a interface de linha de comando (CLI) para executar tarefas básicas.
categories: []
keywords: []
weight: 20
aliases: [/overview/usage/,/extras/livereload/,/doc/usage/,/usage/]
---

## Teste sua instalação

Após [instalar] o Hugo, teste sua instalação executando:

```sh
hugo version
```

Você deve ter algo como:

```text
hugo v0.123.0-3c8a4713908e48e6523f058ca126710397aa4ed5+extended linux/amd64 BuildDate=2024-02-19T16:32:38Z VendorInfo=gohugoio
```

## Liste os comandos disponíveis

Para consultar uma lista dos comandos e flags disponíveis:

```sh
hugo help
```

Para obter ajuda com um subcomando, use a flag `--help`.
Por exemplo:

```sh
hugo server --help
```

## Construa seu site

Para construir seu site, acesse o diretório do seu projeto e então execute:

```sh
hugo
```

O comando [`hugo`] constrói seu site, publicando os arquivos no diretório
público.
Para publicar seu site em um diretório diferente, use a flag [`--destination`]
ou defina [`publishDir`] na configuração do seu site.

> [!note]
> O Hugo não limpa o diretório `public` antes de construir seu site.
> Arquivos existentes são substituídos, mas não excluídos.
> Esse comportamento é intencional para evitar a remoção inadvertida de arquivos
> que você pode ter adicionado ao diretório `public` após a construção.
>
> Dependendo das suas necessidades, você pode querer limpar manualmente o
> conteúdo do diretório `public` antes de cada construção.

## Conteúdo de rascunho, futuro e expirado

O Hugo permite que você defina `draft` (rascunho), `date`, `publishDate` e
`expiryDate` na front matter do seu conteúdo.
Por padrão, o Hugo não publicará conteúdo quando:

- O valor de `draft` for `true`
- A data `date` estiver no futuro
- A data `publishDate` estiver no futuro
- A data `expiryDate` estiver no passado

{{< new-in 0.123.0 />}}

> [!note]
> O Hugo publica descendentes de páginas [node](g) de rascunho, futuras e
> expiradas.
> Para impedir a publicação desses descendentes, use o campo de front matter
> [`cascade`] para cascatear [opções de compilação] para as páginas
> descendentes.

Você pode substituir o comportamento padrão ao executar `hugo` ou `hugo server`
com flags de linha de comando:

```sh
hugo --buildDrafts    # ou -D
hugo --buildExpired   # ou -E
hugo --buildFuture    # ou -F
```

Embora você também possa definir esses valores na configuração do seu site, isso
pode levar a resultados indesejados, a menos que todas as pessoas autoras de
conteúdo estejam cientes e entendam as configurações.

> [!note]
> Conforme observado acima, o Hugo não limpa o diretório `public` antes de
> construir seu site.
> Dependendo da avaliação _atual_ das quatro condições acima, após a construção,
> seu diretório `public` pode conter arquivos estranhos de uma construção
> anterior.
>
> Uma prática comum é limpar manualmente o conteúdo do diretório `public` antes
> de cada construção para remover conteúdo de rascunho, expirado e futuro.

## Desenvolva e teste seu site

Para visualizar seu site enquanto desenvolve layouts ou cria conteúdo, acesse o
diretório do seu projeto e execute:

```sh
hugo server
```

O comando [`hugo server`] constrói seu site e serve suas páginas usando um
servidor HTTP mínimo.
Quando você executa `hugo server`, ele exibe a URL do seu site local:

```text
Web Server is available at http://localhost:1313/ 
```

Enquanto o servidor está em execução, ele observa o diretório do seu projeto em
busca de alterações em assets, configuração, conteúdo, dados, layouts, traduções
e arquivos estáticos.
Quando detecta uma alteração, o servidor reconstrói seu site e atualiza seu
navegador usando o [LiveReload].

A maioria das construções do Hugo são tão rápidas que você pode não notar a
alteração, a menos que esteja acompanhando pelo navegador no momento.

### LiveReload

Enquanto o servidor está em execução, o Hugo injeta JavaScript nas páginas HTML
geradas.
O script LiveReload cria uma conexão do navegador para o servidor por meio de
web sockets.
Você não precisa instalar nenhum programa ou plugin do navegador, nem é
necessária nenhuma configuração.

### Redirecionamento automático

Ao editar o conteúdo, se quiser que seu navegador redirecione automaticamente
para a página modificada pela última vez, execute:

```sh
hugo server --navigateToChanged
```

## Implante seu site

> [!note]
> Conforme observado acima, o Hugo não limpa o diretório `public` antes de
> construir seu site.
> Limpe manualmente o conteúdo do diretório `public` antes de cada construção
> para remover conteúdo de rascunho, expirado e futuro.

Quando estiver pronto para implantar seu site, execute:

```sh
hugo
```

Isso constrói seu site, publicando os arquivos no diretório `public`.
A estrutura do diretório será parecida com esta:

```text
public/
├── categories/
│   ├── index.html
│   └── index.xml  <-- Feed RSS para esta seção
├── posts/
│   ├── meu-primeiro-post/
│   │   └── index.html
│   ├── index.html
│   └── index.xml  <-- Feed RSS para esta seção
├── tags/
│   ├── index.html
│   └── index.xml  <-- Feed RSS para esta seção
├── index.html
├── index.xml      <-- Feed RSS para o site
└── sitemap.xml
```

Em um ambiente de hospedagem simples, onde você normalmente usa `ftp`, `rsync`
ou `scp` para enviar seus arquivos para a raiz de um host virtual, o conteúdo do
diretório `public` é tudo o que você precisa.

A maioria das nossas pessoas usuárias implanta seus sites usando um fluxo de
trabalho de [CI/CD](g), onde um push[^1] para seu repositório GitHub ou GitLab
aciona uma construção e implantação.
Os provedores populares incluem [AWS Amplify], [CloudCannon],
[Cloudflare Pages], [GitHub Pages], [GitLab Pages] e [Netlify].

Saiba mais na seção [hospedagem e implantação].

[^1]: O repositório Git contém todo o diretório do projeto, normalmente
excluindo o diretório `public` porque o site é construído _após_ o push.

[AWS Amplify]: https://aws.amazon.com/amplify/

[`cascade`]: /content-management/front-matter/#cascade

[CloudCannon]: https://cloudcannon.com/

[Cloudflare Pages]: https://pages.cloudflare.com/

[`--destination`]: /commands/hugo/#options

[front matter]: /content-management/front-matter/

[GitHub Pages]: https://pages.github.com/

[GitLab Pages]: https://docs.gitlab.com/ee/user/project/pages/

[hospedagem e implantação]: /host-and-deploy/

[`hugo`]: /commands/hugo/

[`hugo server`]: /commands/hugo_server/

[instalar]: /installation/

[LiveReload]: https://github.com/livereload/livereload-js

[Netlify]: https://www.netlify.com/

[opções de compilação]: /content-management/build-options/

[`publishDir`]: /configuration/all/#publishdir
