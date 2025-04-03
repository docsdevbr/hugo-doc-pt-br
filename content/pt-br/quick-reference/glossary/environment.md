---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: environment
---

Typically one of `development`, `staging`, or `production`, each _environment_ may exhibit different behavior depending on configuration and template logic. For example, in a production environment you might minify and fingerprint CSS, but that probably doesn't make sense in a development environment.

  When running the built-in development server with the `hugo server` command, the environment is set to `development`. When building your site with the `hugo` command, the environment is set to `production`. To override the environment value, use the `--environment` command line flag or the `HUGO_ENVIRONMENT` environment variable.

  To determine the current environment within a template, use the [`hugo.Environment`](/functions/hugo/environment/) function.
