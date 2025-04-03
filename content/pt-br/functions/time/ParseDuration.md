---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: time.ParseDuration
description: Returns a time.Duration value by parsing the given duration string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: time.Duration
    signatures: [time.ParseDuration DURATION]
aliases: [/functions/time.parseduration]
---

The `time.ParseDuration` function returns a time.Duration value that you can use with any of the `Duration` [methods].

A duration string is a possibly signed sequence of decimal numbers, each with optional fraction and a unit suffix, such as `300ms`, `-1.5h` or `2h45m`. Valid time units are `ns`, `us` (or `µs`), `ms`, `s`, `m`, `h`.

This template:

```go-html-template
{{ $duration := time.ParseDuration "24h" }}
{{ printf "There are %.0f seconds in one day." $duration.Seconds }}
```

Is rendered to:

```text
There are 86400 seconds in one day.
```

[`time.Duration`]: https://pkg.go.dev/time#Duration
[methods]: /methods/duration/
