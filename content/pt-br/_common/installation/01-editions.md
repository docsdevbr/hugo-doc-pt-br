---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/installation/01-editions.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

O Hugo está disponível em três edições: padrão, estendida e
estendida/implantação.
Enquanto a edição padrão oferece funcionalidades básicas, as edições estendida e
estendida/implantação oferecem recursos avançados.

 Recurso                                                                                                                                           |  edição estendida  | edição estendida/implantação
:--------------------------------------------------------------------------------------------------------------------------------------------------|:------------------:|:----------------------------:
 Codifique para o formato WebP ao [processar imagens]. Você pode decodificar imagens WebP com qualquer edição.                                     | :heavy_check_mark: |      :heavy_check_mark:
 [Transpile Sass para CSS] usando o transpilador LibSass incorporado. Você pode usar o transpilador [Dart Sass] com qualquer edição.               | :heavy_check_mark: |      :heavy_check_mark:
 Implante seu site diretamente em um bucket do Google Cloud Storage, um bucket do AWS S3 ou um contêiner do Azure Storage. Consulte os [detalhes]. |        :x:         |      :heavy_check_mark:

[Dart Sass]: /functions/css/sass/#dart-sass

[detalhes]: /host-and-deploy/deploy-with-hugo-deploy/

[processar imagens]: /content-management/image-processing/

[Transpile Sass para CSS]: /functions/css/sass/
