---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Logging
description: Enable logging to inspect events while building your site.
categories: []
keywords: []
---

## Command line

Enable console logging with the `--logLevel` command line flag.

Hugo has four logging levels:

error
: Display error messages only.

  ```sh
  hugo --logLevel error
  ```

warn
: Display warning and error messages.

  ```sh
  hugo --logLevel warn
  ```

info
: Display information, warning, and error messages.

  ```sh
  hugo --logLevel info
  ```

debug
: Display debug, information, warning, and error messages.

  ```sh
  hugo --logLevel debug
  ```

> [!note]
> If you do not specify a logging level with the `--logLevel` flag, warnings and errors are always displayed.

## Template functions

You can also use template functions to print warnings or errors to the console. These functions are typically used to report data validation errors, missing files, etc.

{{% list-pages-in-section path=/functions/fmt filter=functions_fmt_logging filterType=include %}}

## LiveReload

To log Hugo's LiveReload requests in your browser, add this query string to the URL when running Hugo's development server:

```text
debug=LR-verbose
```

For example:

```text
http://localhost:1313/?debug=LR-verbose
```

Then monitor the reload requests in your browser's dev tools console. Make sure the dev tools "preserve log" option is enabled.
