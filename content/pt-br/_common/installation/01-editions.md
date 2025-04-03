---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

_comment: Do not remove front matter.
---

Hugo is available in three editions: standard, extended, and extended/deploy. While the standard edition provides core functionality, the extended and extended/deploy editions offer advanced features.

Feature|extended edition|extended/deploy edition
:--|:-:|:-:
Encode to the WebP format when [processing images]. You can decode WebP images with any edition.|:heavy_check_mark:|:heavy_check_mark:
[Transpile Sass to CSS] using the embedded LibSass transpiler. You can use the [Dart Sass] transpiler with any edition.|:heavy_check_mark:|:heavy_check_mark:
Deploy your site directly to a Google Cloud Storage bucket, an AWS S3 bucket, or an Azure Storage container. See&nbsp;[details].|:x:|:heavy_check_mark:

[dart sass]: /functions/css/sass/#dart-sass
[processing images]: /content-management/image-processing/
[transpile sass to css]: /functions/css/sass/
[details]: /host-and-deploy/deploy-with-hugo-deploy/
