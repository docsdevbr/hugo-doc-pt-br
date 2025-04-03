---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Introduction
description: A brief introduction to Hugo Modules.
categories: []
keywords: []
weight: 10
---

Hugo uses modules as its fundamental organizational units. A module can be a full Hugo project or a smaller, reusable piece providing one or more of Hugo's seven component types: static files, content, layouts, data, assets, internationalization (i18n) resources, and archetypes.

Modules are combinable in any arrangement, and external directories (including those from non-Hugo projects) can be mounted, effectively creating a single, unified file system.

Some example projects:

[https://github.com/bep/docuapi](https://github.com/bep/docuapi)
: A theme that has been ported to Hugo Modules while testing this feature. It is a good example of a non-Hugo-project mounted into Hugo's directory structure. It even shows a JS Bundler implementation in regular Go templates.

[https://github.com/bep/my-modular-site](https://github.com/bep/my-modular-site)
: A simple site used for testing.
