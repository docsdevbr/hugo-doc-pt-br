---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/about/security.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

title: Modelo de segurança
linkTitle: Segurança
description: Um resumo do modelo de segurança do Hugo.
categories: []
keywords: []
weight: 30
aliases: [/about/security-model/]
---

## Segurança do tempo de execução

O Hugo gera sites estáticos, o que significa que a saída final é executada
diretamente no navegador e interage com quaisquer APIs integradas.
No entanto, durante o desenvolvimento e a construção do site, o próprio
executável `hugo` é o ambiente de tempo de execução.

Proteger um tempo de execução é uma tarefa complexa.
O Hugo aborda isso por meio de uma abordagem de sandbox robusta e uma política
de segurança rigorosa com proteções padrão.
Os principais recursos incluem:

- Sistema de arquivos virtual: o Hugo emprega um sistema de arquivos virtual,
  limitando o acesso aos arquivos.
  Apenas o projeto principal, não componentes externos, pode acessar arquivos ou
  diretórios fora da raiz do projeto.
- Acesso somente leitura: componentes definidos pela pessoa usuária têm acesso
  somente leitura ao sistema de arquivos, evitando modificações não
  intencionais.
- Binários externos controlados: embora o Hugo utilize binários externos para
  recursos como suporte ao Asciidoctor, eles são estritamente predefinidos com
  flags específicas e são desabilitados por padrão.
  A [política de segurança] detalha essas limitações.
- Sem comandos arbitrários: para mitigar riscos, o Hugo evita intencionalmente
  implementar funções gerais que permitiriam às pessoas usuárias executar
  comandos arbitrários do sistema operacional.

Essa combinação de sandbox e padrões rigorosos minimiza efetivamente potenciais
vulnerabilidades de segurança durante o processo de construção do Hugo.

[política de segurança]: /configuration/security/

## Segurança de dependência

O Hugo utiliza [Módulos Go] para gerenciar suas dependências, compilando como um
binário estático.
Os [Módulos Go] criam um arquivo `go.sum`, um recurso de segurança crítico.
Este arquivo atua como um banco de dados, armazenando os checksums
criptográficos esperados de todas as dependências, incluindo aquelas requeridas
indiretamente (dependências transitivas).

Os [Módulos Hugo], que estendem a funcionalidade dos Módulos Go, também produzem
um arquivo `go.sum`.
Para garantir a integridade das dependências, envie este arquivo `go.sum` para
seu controle de versão.
Se o Hugo detectar uma incompatibilidade de checksum durante o processo de
construção, ele falhará, indicando uma possível tentativa de
[adulterar as dependências do seu projeto].

[adulterar as dependências do seu projeto]: https://julienrenaux.fr/2019/12/20/github-actions-security-risk/

[Módulos Go]: https://go.dev/wiki/Modules#modules

[Módulos Hugo]: /hugo-modules/

## Segurança de aplicações web

A filosofia de segurança do Hugo está enraizada em padrões de segurança
estabelecidos, alinhando-se principalmente com as ameaças definidas pelo
[OWASP].
Para saída HTML, o Hugo opera sob um modelo de confiança claro.
Este modelo pressupõe que as pessoas autoras de templates e configurações, as
pessoas desenvolvedoras, são confiáveis.
No entanto, os dados fornecidos a esses templates são inerentemente considerados
não confiáveis.
Essa distinção é crucial para entender como o Hugo lida com potenciais riscos de
segurança.

[OWASP]: https://en.wikipedia.org/wiki/OWASP

Para evitar o escape não intencional de dados que as pessoas desenvolvedoras
sabem que são seguros, o Hugo fornece funções [`safe`], como [`safeHTML`].
Essas funções permitem que as pessoas desenvolvedoras marquem explicitamente os
dados como confiáveis, ignorando os mecanismos de escape padrão.
Isso é essencial para cenários em que os dados são gerados ou obtidos de fontes
confiáveis.
No entanto, existe uma exceção: habilitar [shortcodes em linha].
Ao ativar esse recurso, você está confiando implicitamente na lógica dentro dos
shortcodes e nos dados contidos em seus arquivos de conteúdo.

[`safeHTML`]: /functions/safe/html/

[shortcodes em linha]: /content-management/shortcodes/#inline

É vital lembrar que o Hugo é um gerador de site estático.
Essa escolha arquitetônica reduz significativamente a superfície de ataque,
eliminando as complexidades e vulnerabilidades associadas à entrada dinâmica de
dados da pessoa usuária.
Ao contrário dos sites dinâmicos, o Hugo gera arquivos HTML estáticos,
minimizando o risco de ataques em tempo real.
Em relação ao conteúdo, o renderizador Markdown padrão do Hugo é
[configurado para sanitizar] conteúdo potencialmente inseguro.
Esse comportamento padrão garante que códigos ou scripts potencialmente
maliciosos sejam removidos ou escapados.
No entanto, essa configuração pode ser reconfigurada se você tiver um alto grau
de confiança na segurança de suas fontes de conteúdo.

[configurado para sanitizar]: /configuration/markup/#rendererunsafe

Em essência, o Hugo prioriza a saída segura estabelecendo um limite de confiança
claro entre pessoas desenvolvedoras e dados.
Por padrão, ele erra por excesso de cautela, sanitizando conteúdo potencialmente
inseguro e escapando dados.
As pessoas desenvolvedoras têm a flexibilidade de ajustar esses padrões por meio
de funções [`safe`] e [opções de configuração], mas devem fazer isso com uma
compreensão clara das implicações de segurança.
O modelo de geração de site estático do Hugo fortalece ainda mais sua postura de
segurança minimizando vulnerabilidades dinâmicas.

[`safe`]: /functions/safe

[opções de configuração]: /configuration/security

## Configuração

Consulte [Configure a segurança](/configuration/security/).
