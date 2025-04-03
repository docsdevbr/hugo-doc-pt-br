---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: transform.Emojify 
description: Runs a string through the Emoji emoticons processor.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [emojify]
    returnType: template.HTML
    signatures: [transform.Emojify INPUT]
aliases: [/functions/emojify]
---

`emojify` runs a passed string through the Emoji emoticons processor.

See the list of [emoji shortcodes] for available emoticons.

The `emojify` function can be called in your templates but not directly in your content files by default. For emojis in content files, set [`enableEmoji`] to `true` in your site's configuration. Then you can write emoji shorthand directly into your content files;

```text
I :heart: Hugo!
```

I :heart: Hugo!

[`enableEmoji`]: /configuration/all/#enableemoji
[emoji shortcodes]: /quick-reference/emojis/
