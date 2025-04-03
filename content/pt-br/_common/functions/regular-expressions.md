---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

_comment: Do not remove front matter.
---

When specifying the regular expression, use a raw [string literal] (backticks) instead of an interpreted string literal (double quotes) to simplify the syntax. With an interpreted string literal you must escape backslashes.

Go's regular expression package implements the [RE2 syntax]. The RE2 syntax is a subset of that accepted by [PCRE], roughly speaking, and with various [caveats]. Note that the RE2 `\C` escape sequence is not supported.

[caveats]: https://swtch.com/~rsc/regexp/regexp3.html#caveats
[PCRE]: https://www.pcre.org/
[RE2 syntax]: https://github.com/google/re2/wiki/Syntax/
[string literal]: https://go.dev/ref/spec#String_literals
