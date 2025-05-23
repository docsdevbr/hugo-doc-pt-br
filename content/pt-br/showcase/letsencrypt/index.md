---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Let's Encrypt
date: 2018-03-13
description: 'Showcase: "Lessons learned from taking letsencrypt.org to Hugo."'
siteURL: https://letsencrypt.org/
siteSource: https://github.com/letsencrypt/website
byline: "[bep](https://github.com/bep), Hugo Lead"
---

The **Let's Encrypt website** has a common set of elements: A landing page and some other static info-pages, a document section, a blog, and a documentation section. Having it moved to Hugo was mostly motivated by a _simpler administration and Hugo's [multilingual support](/content-management/multilingual/)_. They already serve HTTPS to more than 60 million domains, and having the documentation available in more languages will increase that reach.[^1]

{{< x user="letsencrypt" id="971755920639307777" >}}

I helped them port the site from Jekyll to Hugo. There are usually very few surprises doing this. I know Hugo very well, but working on sites with a history usually comes up with something new.

That site is bookmarked in many browsers, so preserving the URLs was a must. Hugo's URL handling is very flexible, but there was one challenge. The website has a mix of standard and what we in Hugo call _ugly URLs_ (`https://letsencrypt.org/2017/12/07/looking-forward-to-2018.html`). In Hugo this is handled automatically, and you can turn it on globally or per language. But before Hugo `0.33` you could not configure it for parts of your site. You could set it manually for the relevant pages in front matter -- which is how it was done in Jekyll -- but that would be hard to manage, especially when you start to introduce translations. So, in Hugo 0.33 I added support for _ugly URLs_ per section and also `url` set in front matter for list pages (`https://letsencrypt.org/blog/`).

[^1]: The work on getting the content translated is in progress.
