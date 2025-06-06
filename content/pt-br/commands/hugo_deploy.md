---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: "hugo deploy"
slug: hugo_deploy
url: /commands/hugo_deploy/
---
## hugo deploy

Deploy your site to a cloud provider

### Synopsis

Deploy your site to a cloud provider

See https://gohugo.io/hosting-and-deployment/hugo-deploy/ for detailed
documentation.


```
hugo deploy [flags] [args]
```

### Options

```
      --confirm          ask for confirmation before making changes to the target
      --dryRun           dry run
      --force            force upload of all files
  -h, --help             help for deploy
      --invalidateCDN    invalidate the CDN cache listed in the deployment target (default true)
      --maxDeletes int   maximum # of files to delete, or -1 to disable (default 256)
      --target string    target deployment from deployments section in config file; defaults to the first one
      --workers int      number of workers to transfer files. defaults to 10 (default 10)
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

