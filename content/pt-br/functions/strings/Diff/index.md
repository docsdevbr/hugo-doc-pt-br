---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: strings.Diff
description: Returns an anchored diff of the two texts OLD and NEW in the unified diff format. If OLD and NEW are identical, returns an empty string.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [strings.Diff OLDNAME OLD NEWNAME NEW]
---

{{< new-in 0.125.0 />}}

Use `strings.Diff` to compare two strings and render a highlighted diff:

```go-html-template
{{ $want := `
<p>The product of 6 and 7 is 42.</p>
<p>The product of 7 and 6 is 42.</p>
`}}

{{ $got := `
<p>The product of 6 and 7 is 42.</p>
<p>The product of 7 and 6 is 13.</p>
`}}

{{ $diff := strings.Diff "want" $want "got" $got }}
{{ transform.Highlight $diff "diff" }}
```

Rendered:

![screen capture](diff-screen-capture.png)
