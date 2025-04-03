---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Page collections
description: A quick reference guide to Hugo's page collections.
categories: []
keywords: []
---

## Page

Use these `Page` methods when rendering lists on [section pages](g), [taxonomy pages](g), [term pages](g), and the home page.

{{% list-pages-in-section path=/methods/page filter=methods_page_page_collections filterType=include titlePrefix=PAGE. %}}

## Site

Use these `Site` methods when rendering lists on any page.

{{% list-pages-in-section path=/methods/site filter=methods_site_page_collections filterType=include titlePrefix=SITE. %}}

## Filter

Use the [`where`] function to filter page collections.

## Sort

{{% glossary-term "default sort order" %}}

Use these methods to sort page collections by different criteria.

{{% list-pages-in-section path=/methods/pages filter=methods_pages_sort filterType=include titlePrefix=. titlePrefix=PAGES. %}}

## Group

Use these methods to group page collections.

{{% list-pages-in-section path=/methods/pages filter=methods_pages_group filterType=include titlePrefix=. titlePrefix=PAGES. %}}

[`where`]: /functions/collections/where/
