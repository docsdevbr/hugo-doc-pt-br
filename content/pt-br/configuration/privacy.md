---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Configure privacy
linkTitle: Privacy
description: Configure your site to help comply with regional privacy regulations.
categories: []
keywords: []
aliases: [/about/privacy/]
---

## Responsibility

Site authors are responsible for ensuring compliance with regional privacy regulations, including but not limited to:

- GDPR (General Data Protection Regulation): Applies to individuals within the European Union and the European Economic Area.
- CCPA (California Consumer Privacy Act): Applies to California residents.
- CPRA (California Privacy Rights Act): Expands upon the CCPA with stronger consumer privacy protections.
- Virginia Consumer Data Protection Act (CDPA): Applies to businesses that collect, process, or sell the personal data of Virginia residents.

Hugo's privacy settings can assist in compliance efforts.

## Embedded templates

Hugo provides [embedded templates](g) to simplify site and content creation. Some of these templates interact with external services. For example, the `youtube` shortcode connects with YouTube's servers to embed videos on your site.

Some of these templates include settings to enhance privacy.

## Configuration

> [!note]
> These settings affect the behavior of some of Hugo's embedded templates. These settings may or may not affect the behavior of templates provided by third parties in their modules or themes.

These are the default privacy settings for Hugo's embedded templates:

{{< code-toggle config=privacy />}}

See each template's documentation for a description of its privacy settings:

- [Disqus partial](/templates/embedded/#privacy-disqus)
- [Google Analytics partial](/templates/embedded/#privacy-google-analytics)
- [Instagram shortcode](/shortcodes/instagram/#privacy)
- [Vimeo shortcode](/shortcodes/vimeo/#privacy)
- [X shortcode](/shortcodes/x/#privacy)
- [YouTube shortcode](/shortcodes/youtube/#privacy)
