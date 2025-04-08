---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/functions/js/options.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

params
: (`map` ou `slice`) Parâmetros que podem ser importados como JSON em seus
arquivos JS, por exemplo.

  ```go-html-template
  {{ $js := resources.Get "js/main.js" | js.Build (dict "params" (dict "api" "https://example.org/api")) }}
  ```

  E então em seu arquivo JS:

  ```js
  import * as params from '@params';
  ```

  Observe que isso é destinado a pequenos conjuntos de dados, por exemplo,
  definições de configuração.
  Para conjuntos de dados maiores, coloque/monte os arquivos em `assets` e
  importe-os diretamente.

minify
: (`bool`) Se deve deixar `js.Build` lidar com a minificação.

loaders
: {{< new-in 0.140.0 />}}
: (`map`) Configurar um carregador para um determinado tipo de arquivo permite
que você carregue esse tipo de arquivo com uma instrução `import` ou uma chamada
`require`.
Por exemplo, configurar a extensão de arquivo `.png` para usar o carregador de
URL de dados significa que importar um arquivo `.png` fornece uma URL de dados
contendo o conteúdo dessa imagem.
Os carregadores disponíveis são `none`, `base64`, `binary`, `copy`, `css`,
`dataurl`, `default`, `empty`, `file`, `global-css`, `js`, `json`, `jsx`,
`local-css`, `text`, `ts`, `tsx`.
Consulte https://esbuild.github.io/api/#loader.

inject
: (`slice`) Esta opção permite que você substitua automaticamente uma variável
global por uma importação de outro arquivo.
Os nomes de caminho devem ser relativos a `assets`.
Consulte https://esbuild.github.io/api/#inject.

shims
: (`map`) Esta opção permite trocar um componente por outro.
Um caso de uso comum é carregar dependências como React de uma CDN (com _shims_)
quando em produção, mas rodar com a dependência `node_modules` completa durante
o desenvolvimento:

  ```go-html-template
  {{ $shims := dict "react" "js/shims/react.js"  "react-dom" "js/shims/react-dom.js" }}
  {{ $js = $js | js.Build dict "shims" $shims }}
  ```

  Os arquivos _shim_ podem se parecer com estes:

  ```js
  // js/shims/react.js
  module.exports = window.React;
  ```

  ```js
  // js/shims/react-dom.js
  module.exports = window.ReactDOM;
  ```

  Com o código acima, essas importações devem funcionar em ambos os cenários:

  ```js
  import * as React from 'react';
  import * as ReactDOM from 'react-dom/client';
  ```

target
: (`string`) O destino da linguagem.
Uma das seguintes opções: `es5`, `es2015`, `es2016`, `es2017`, `es2018`,
`es2019`, `es2020`, `es2021`, `es2022`, `es2023`, `es2024` ou `esnext`.
O padrão é `esnext`.

platform
: {{< new-in 0.140.0 />}}
: (`string`) Uma das seguintes opções: `browser`, `node` ou `neutral`.
O padrão é `browser`.
Consulte https://esbuild.github.io/api/#platform.

externals
: (`slice`) Dependências externas.
Use isso para reduzir dependências que você sabe que nunca serão executadas.
Consulte https://esbuild.github.io/api/#external.

defines
: (`map`) Permite definir um conjunto de substituição de strings a ser executado
durante a construção.
Deve ser um mapa onde cada chave deve ser substituída por seu valor.

  ```go-html-template
  {{ $defines := dict "process.env.NODE_ENV" `"development"` }}
  ```

drop
: {{< new-in 0.144.0 />}}
: (`string`) Edite seu código-fonte antes da construção para remover certas
construções. Uma das seguintes opções: `debugger` ou `console`.
Consulte https://esbuild.github.io/api/#drop

sourceMap
: (`string`) Se deve gerar mapas de origem `inline` (em linha), `linked`
(vinculados) ou `external` (externos) do esbuild.
Mapas de origem vinculados e externos serão gravados no destino com o nome do
arquivo de saída + ".map".
Ao usar `linked`, uma `sourceMappingURL` também será gravada no arquivo de
saída.
Por padrão, os mapas de origem não são criados.
Observe que a opção `linked` foi adicionada no Hugo 0.140.0.

sourcesContent
: {{< new-in 0.140.0 />}}
: (`bool`) Se deve incluir o conteúdo dos arquivos de origem no mapa de origem.
Por padrão, isso é `true`.

JSX
: {{< new-in 0.124.0 />}}
: (`string`) Como manipular/transformar a sintaxe JSX.
Uma das seguintes opções: `transform`, `preserve` ou `automatic`.
O padrão é `transform`.
Notavelmente, a transformação `automatic` foi introduzida no React 17+ e fará
com que as funções auxiliares JSX necessárias sejam importadas automaticamente.
Consulte https://esbuild.github.io/api/#jsx.

JSXImportSource
: {{< new-in 0.124.0 />}}
: (`string`) Qual biblioteca usar para importar automaticamente suas funções
auxiliares JSX.
Isso só funciona se `JSX` estiver definido como `automatic`.
A biblioteca especificada precisa ser instalada por meio do npm e expor certas
exportações.
Consulte https://esbuild.github.io/api/#jsx-import-source.

  A combinação de `JSX` e `JSXImportSource` é útil se você quiser usar uma
  biblioteca JSX não React como Preact, por exemplo:

  ```go-html-template
  {{ $js := resources.Get "js/main.jsx" | js.Build (dict "JSX" "automatic" "JSXImportSource" "preact") }}
  ```

  Com o código acima, você pode usar componentes Preact e JSX sem ter que sempre
  importar manualmente `h` e `Fragment`:

  ```jsx
  import { render } from 'preact';

  const App = () => <>Olá, mundo!</>;

  const container = document.getElementById('app');
  if (container) render(<App />, container);
  ```
