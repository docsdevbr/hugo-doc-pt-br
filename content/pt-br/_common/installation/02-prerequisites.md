---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/installation/02-prerequisites.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

## Pré-requisitos

Embora não sejam obrigatórios em todos os casos, [Git], [Go] e [Dart Sass] são
comumente usados ao trabalhar com o Hugo.

O Git é necessário para:

- Compilar o Hugo a partir do código-fonte
- Usar o recurso [Módulos do Hugo]
- Instalar um tema como um submódulo do Git
- Acessar [informações de commit] de um repositório Git local
- Hospedar seu site com serviços como [CloudCannon], [Cloudflare Pages],
  [GitHub Pages], [GitLab Pages] e [Netlify]

O Go é necessário para:

- Compilar o Hugo a partir do código-fonte
- Usar o recurso Módulos do Hugo

O Dart Sass é necessário para transpilar o Sass para CSS ao usar os recursos
mais recentes da linguagem Sass.

Consulte a documentação relevante para obter instruções de instalação:

- [Git][git install]
- [Go][go install]
- [Dart Sass][dart sass install]

[CloudCannon]: https://cloudcannon.com/

[Cloudflare Pages]: https://pages.cloudflare.com/

[dart sass install]: /functions/css/sass/#dart-sass

[Dart Sass]: https://sass-lang.com/dart-sass

[Git]: https://git-scm.com/

[git install]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

[GitHub Pages]: https://pages.github.com/

[GitLab Pages]: https://docs.gitlab.com/ee/user/project/pages/

[Go]: https://go.dev/

[go install]: https://go.dev/doc/install

[netlify]: https://www.netlify.com/
