---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: "hugo"
slug: hugo
url: /commands/hugo/
---
## hugo

Build your site

### Synopsis

hugo is the main command, used to build your Hugo site.

Hugo is a Fast and Flexible Static Site Generator
built with love by spf13 and friends in Go.

Complete documentation is available at https://gohugo.io/.

```
hugo [flags]
```

### Options

```
  -b, --baseURL string             hostname (and path) to the root, e.g. https://spf13.com/
  -D, --buildDrafts                include content marked as draft
  -E, --buildExpired               include expired content
  -F, --buildFuture                include content with publishdate in the future
      --cacheDir string            filesystem path to cache directory
      --cleanDestinationDir        remove files from destination not found in static directories
      --clock string               set the clock used by Hugo, e.g. --clock 2021-11-06T22:30:00.00+09:00
      --config string              config file (default is hugo.yaml|json|toml)
      --configDir string           config dir (default "config")
  -c, --contentDir string          filesystem path to content directory
  -d, --destination string         filesystem path to write files to
      --disableKinds strings       disable different kind of pages (home, RSS etc.)
      --enableGitInfo              add Git revision, date, author, and CODEOWNERS info to the pages
  -e, --environment string         build environment
      --forceSyncStatic            copy all files when static is changed.
      --gc                         enable to run some cleanup tasks (remove unused cache files) after the build
  -h, --help                       help for hugo
      --ignoreCache                ignores the cache directory
      --ignoreVendorPaths string   ignores any _vendor for module paths matching the given Glob pattern
  -l, --layoutDir string           filesystem path to layout directory
      --logLevel string            log level (debug|info|warn|error)
      --minify                     minify any supported output format (HTML, XML etc.)
      --noBuildLock                don't create .hugo_build.lock file
      --noChmod                    don't sync permission mode of files
      --noTimes                    don't sync modification time of files
      --panicOnWarning             panic on first WARNING log
      --poll string                set this to a poll interval, e.g --poll 700ms, to use a poll based approach to watch for file system changes
      --printI18nWarnings          print missing translations
      --printMemoryUsage           print memory usage to screen at intervals
      --printPathWarnings          print warnings on duplicate target paths etc.
      --printUnusedTemplates       print warnings on unused templates.
      --quiet                      build in quiet mode
      --renderSegments strings     named segments to render (configured in the segments config)
  -M, --renderToMemory             render to memory (mostly useful when running the server)
  -s, --source string              filesystem path to read files relative from
      --templateMetrics            display metrics about template executions
      --templateMetricsHints       calculate some improvement hints when combined with --templateMetrics
  -t, --theme strings              themes to use (located in /themes/THEMENAME/)
      --themesDir string           filesystem path to themes directory
      --trace file                 write trace to file (not useful in general)
  -w, --watch                      watch filesystem for changes and recreate as needed
```

### SEE ALSO

* [hugo build](/commands/hugo_build/)	 - Build your site
* [hugo completion](/commands/hugo_completion/)	 - Generate the autocompletion script for the specified shell
* [hugo config](/commands/hugo_config/)	 - Display site configuration
* [hugo convert](/commands/hugo_convert/)	 - Convert front matter to another format
* [hugo deploy](/commands/hugo_deploy/)	 - Deploy your site to a cloud provider
* [hugo env](/commands/hugo_env/)	 - Display version and environment info
* [hugo gen](/commands/hugo_gen/)	 - Generate documentation and syntax highlighting styles
* [hugo import](/commands/hugo_import/)	 - Import a site from another system
* [hugo list](/commands/hugo_list/)	 - List content
* [hugo mod](/commands/hugo_mod/)	 - Manage modules
* [hugo new](/commands/hugo_new/)	 - Create new content
* [hugo server](/commands/hugo_server/)	 - Start the embedded web server
* [hugo version](/commands/hugo_version/)	 - Display version

