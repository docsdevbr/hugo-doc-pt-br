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

## Dependency security

Hugo utilizes [Go Modules] to manage its dependencies, compiling as a static binary. Go Modules create a `go.sum` file, a critical security feature. This file acts as a database, storing the expected cryptographic checksums of all dependencies, including those required indirectly (transitive dependencies).

[Hugo Modules], which extend Go Modules' functionality, also produce a `go.sum` file. To ensure dependency integrity, commit this `go.sum` file to your version control. If Hugo detects a checksum mismatch during the build process, it will fail, indicating a possible attempt to [tamper with your project's dependencies].

[Go Modules]: https://go.dev/wiki/Modules#modules
[Hugo Modules]: /hugo-modules/
[tamper with your project's dependencies]: https://julienrenaux.fr/2019/12/20/github-actions-security-risk/

## Web application security

Hugo's security philosophy is rooted in established security standards, primarily aligning with the threats defined by [OWASP]. For HTML output, Hugo operates under a clear trust model. This model assumes that template and configuration authors, the developers, are trustworthy. However, the data supplied to these templates is inherently considered untrusted. This distinction is crucial for understanding how Hugo handles potential security risks.

[OWASP]: https://en.wikipedia.org/wiki/OWASP

To prevent unintended escaping of data that developers know is safe, Hugo provides  [`safe`] functions, such as [`safeHTML`]. These functions allow developers to explicitly mark data as trusted, bypassing the default escaping mechanisms. This is essential for scenarios where data is generated or sourced from reliable sources. However, an exception exists: enabling [inline shortcodes]. By activating this feature, you are implicitly trusting the logic within the shortcodes and the data contained within your content files.

[`safeHTML`]: /functions/safe/html/
[inline shortcodes]: /content-management/shortcodes/#inline

It's vital to remember that Hugo is a static site generator. This architectural choice significantly reduces the attack surface by eliminating the complexities and vulnerabilities associated with dynamic user input. Unlike dynamic websites, Hugo generates static HTML files, minimizing the risk of real-time attacks. Regarding content, Hugo's default Markdown renderer is [configured to sanitize] potentially unsafe content. This default behavior ensures that potentially malicious code or scripts are removed or escaped. However, this setting can be reconfigured if you have a high degree of confidence in the safety of your content sources.

[configured to sanitize]: /configuration/markup/#rendererunsafe

In essence, Hugo prioritizes secure output by establishing a clear trust boundary between developers and data. By default, it errs on the side of caution, sanitizing potentially unsafe content and escaping data. Developers have the flexibility to adjust these defaults through [`safe`] functions and [configuration options], but they must do so with a clear understanding of the security implications. Hugo's static site generation model further strengthens its security posture by minimizing dynamic vulnerabilities.

[`safe`]: /functions/safe
[configuration options]: /configuration/security

## Configuration

See [configure security](/configuration/security/).
