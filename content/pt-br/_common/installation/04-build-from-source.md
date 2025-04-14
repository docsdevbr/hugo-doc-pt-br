---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/installation/04-build-from-source.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

## Compilar a partir do código-fonte

Para compilar a edição estendida ou estendida/implantação a partir do
código-fonte, você deve:

1. Instalar o [Git]
1. Instalar o [Go] versão 1.23.0 ou posterior
1. Instalar um compilador C, [GCC] ou [Clang]
1. Atualizar sua variável de ambiente `PATH` conforme descrito na
   [documentação do Go]

> O diretório de instalação é controlado pelas variáveis de ambiente `GOPATH` e
> `GOBIN`.
> Se `GOBIN` estiver definida, os binários serão instalados nesse diretório.
> Se `GOPATH` estiver definida, os binários serão instalados no subdiretório
> `bin` do primeiro diretório na lista `GOPATH`.
> Caso contrário, os binários serão instalados no subdiretório `bin` do `GOPATH`
> padrão (`$HOME/go` ou `%USERPROFILE%\go`).

Para compilar a edição padrão:

```sh
go install github.com/gohugoio/hugo@latest
```

Para compilar a edição estendida:

```sh
CGO_ENABLED=1 go install -tags extended github.com/gohugoio/hugo@latest
```

Para compilar a edição estendida/implantação:

```sh
CGO_ENABLED=1 go install -tags extended,withdeploy github.com/gohugoio/hugo@latest
```

[Clang]: https://clang.llvm.org/

[documentação do Go]: https://go.dev/doc/code#Command

[GCC]: https://gcc.gnu.org/

[Git]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

[Go]: https://go.dev/doc/install
