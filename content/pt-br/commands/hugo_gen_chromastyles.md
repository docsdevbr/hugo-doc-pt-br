---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: "hugo gen chromastyles"
slug: hugo_gen_chromastyles
url: /commands/hugo_gen_chromastyles/
---
## hugo gen chromastyles

Generate CSS stylesheet for the Chroma code highlighter

### Synopsis

Generate CSS stylesheet for the Chroma code highlighter for a given style. This stylesheet is needed if markup.highlight.noClasses is disabled in config.

See https://xyproto.github.io/splash/docs/all.html for a preview of the available styles

```
hugo gen chromastyles [flags] [args]
```

### Options

```
  -h, --help                            help for chromastyles
      --highlightStyle string           foreground and background colors for highlighted lines, e.g. --highlightStyle "#fff000 bg:#000fff"
      --lineNumbersInlineStyle string   foreground and background colors for inline line numbers, e.g. --lineNumbersInlineStyle "#fff000 bg:#000fff"
      --lineNumbersTableStyle string    foreground and background colors for table line numbers, e.g. --lineNumbersTableStyle "#fff000 bg:#000fff"
      --style string                    highlighter style (see https://xyproto.github.io/splash/docs/) (default "friendly")
```

### Options inherited from parent commands

```
      --clock string               set the clock used by Hugo, e.g. --clock 2021-11-06T22:30:00.00+09:00
      --config string              config file (default is hugo.yaml|json|toml)
      --configDir string           config dir (default "config")
  -d, --destination string         filesystem path to write files to
  -e, --environment string         build environment
      --ignoreVendorPaths string   ignores any _vendor for module paths matching the given Glob pattern
      --logLevel string            log level (debug|info|warn|error)
      --noBuildLock                don't create .hugo_build.lock file
      --quiet                      build in quiet mode
  -M, --renderToMemory             render to memory (mostly useful when running the server)
  -s, --source string              filesystem path to read files relative from
      --themesDir string           filesystem path to themes directory
```

### SEE ALSO

* [hugo gen](/commands/hugo_gen/)	 - Generate documentation and syntax highlighting styles

