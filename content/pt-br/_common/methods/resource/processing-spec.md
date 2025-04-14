---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/methods/resource/processing-spec.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

## Especificação do processo

A especificação do processo é uma lista delimitada por espaços e sem distinção
entre maiúsculas e minúsculas, de um ou mais dos seguintes itens em qualquer
sequência:

action
: Aplicável apenas ao método [`Process`](/methods/resource/process).
Especifique zero ou um dos seguintes: `crop`, `fill`, `fit` ou `resize`.
Se você especificar uma `action`, também deverá fornecer `dimensions`.

dimensions
: Forneça a largura _ou_ a altura ao usar o método
[`Resize`](/methods/resource/resize); caso contrário, forneça largura _e_
altura.
Consulte os [detalhes](/content-management/image-processing/#dimensions).

anchor
: Use com os métodos [`Crop`](/methods/resource/crop) e
[`Fill`](/methods/resource/fill).
Especifique zero ou um dos seguintes: `TopLeft`, `Top`, `TopRight`, `Left`,
`Center`, `Right`, `BottomLeft`, `Bottom`, `BottomRight` ou `Smart`.
O padrão é `Smart`.
Consulte os [detalhes](/content-management/image-processing/#anchor).

rotation
: Especifique zero ou um dos seguintes: `r90`, `r180` ou `r270`.
Também suporta ângulos de rotação arbitrários.
Consulte os [detalhes](/content-management/image-processing/#rotation).

target format
: Especifique zero ou um dos seguintes: `gif`, `jpeg`, `png`, `tiff` ou `webp`.
Consulte os [detalhes](/content-management/image-processing/#target-format).

quality
: Aplicável a imagens JPEG e WebP.
Opcionalmente, especifique `qN`, onde `N` é um inteiro no intervalo [0, 100].
O padrão é `75`.
Consulte os [detalhes](/content-management/image-processing/#quality).

hint
: Aplicável a imagens WebP e equivalente à flag `-preset` para o codificador
[`cwebp`].
Especifique zero ou um dos seguintes: `drawing`, `icon`, `photo`, `picture` ou
`text`.
O padrão é `photo`.
Consulte [detalhes](/content-management/image-processing/#hint).

[`cwebp`]: https://developers.google.com/speed/webp/docs/cwebp

background color
: Ao converter um PNG ou WebP com transparência para um formato que não suporta
transparência, opcionalmente especifique uma cor de fundo usando um código de
cor hexadecimal de 3 ou 6 dígitos.
O padrão é `#ffffff` (branco).
Consulte os [detalhes](/content-management/image-processing/#background-color).

resampling filter
: Especifique zero ou um dos seguintes: `Box`, `Lanczos`, `CatmullRom`,
`MitchellNetravali`, `Linear` ou `NearestNeighbor`.
Outros filtros de reamostragem estão disponíveis.
Consulte os [detalhes](/content-management/image-processing/#resampling-filter).
