---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Content types
description: Hugo is built around content organized in sections.
categories: []
keywords: []
aliases: [/content/types]
---

A **content type** is a way to organize your content. Hugo resolves the content type from either the `type` in front matter or, if not set, the first directory in the file path. E.g. `content/blog/my-first-event.md` will be of type `blog` if no `type` is set.

A content type is used to

- Determine how the content is rendered. See [Template Lookup Order](/templates/lookup-order/) and [Content Views](/templates/content-view) for more.
- Determine which [archetype](/content-management/archetypes/) template to use for new content.
