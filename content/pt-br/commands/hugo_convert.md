---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: "hugo convert"
slug: hugo_convert
url: /commands/hugo_convert/
---
## hugo convert

Convert front matter to another format

### Synopsis

Convert front matter to another format.

See convert's subcommands toJSON, toTOML and toYAML for more information.

### Options

```
  -h, --help            help for convert
  -o, --output string   filesystem path to write files to
      --unsafe          enable less safe operations, please backup first
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

* [hugo](/commands/hugo/)	 - Build your site
* [hugo convert toJSON](/commands/hugo_convert_tojson/)	 - Convert front matter to JSON
* [hugo convert toTOML](/commands/hugo_convert_totoml/)	 - Convert front matter to TOML
* [hugo convert toYAML](/commands/hugo_convert_toyaml/)	 - Convert front matter to YAML

