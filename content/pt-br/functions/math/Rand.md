---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: math.Rand
description: Returns a pseudo-random number in the half-open interval [0.0, 1.0).
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: []
    returnType: float64
    signatures: [math.Rand]
---

{{< new-in 0.121.2 />}}

The `math.Rand` function returns a pseudo-random number in the half-open [interval](g) [0.0, 1.0).

```go-html-template
{{ math.Rand }} → 0.6312770459590062
```

To generate a random integer in the closed interval [0, 5]:

```go-html-template
{{ math.Rand | mul 6 | math.Floor }}
```

To generate a random integer in the closed interval [1, 6]:

```go-html-template
{{ math.Rand | mul 6 | math.Ceil }}
```

To generate a random float, with one digit after the decimal point, in the closed interval [0, 4.9]:

```go-html-template
{{ div (math.Rand | mul 50 | math.Floor) 10 }}
```

To generate a random float, with one digit after the decimal point, in the closed interval [0.1, 5.0]:

```go-html-template
{{ div (math.Rand | mul 50 | math.Ceil) 10 }}
```
