---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.

# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: ResourceType
description: Returns the main type of the given resource's media type.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: string
    signatures: [RESOURCE.ResourceType]
---

{{% include "/_common/methods/resource/global-page-remote-resources.md" %}}

Common resource types include `audio`, `image`, `text`, and `video`.

```go-html-template
{{ with resources.Get "image/a.jpg" }}
  {{ .ResourceType }} → image
  {{ .MediaType.MainType }} → image
{{ end }}
```

When working with content files, the resource type is `page`.

```text
content/
├── lessons/
│   ├── lesson-1/
│   │   ├── _objectives.md  <-- resource type = page
│   │   ├── _topics.md      <-- resource type = page
│   │   ├── _example.jpg    <-- resource type = image
│   │   └── index.md
│   └── _index.md
└── _index.md
```

With the structure above, we can range through page resources of type `page` to build content:

```go-html-template {file="layouts/lessons/single.html"}
{{ range .Resources.ByType "page" }}
  {{ .Content }}
{{ end }}
```
