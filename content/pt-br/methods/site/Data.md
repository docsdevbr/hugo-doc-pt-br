---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: Data
description: Returns a data structure composed from the files in the data directory.
categories: []
keywords: []
params:
  functions_and_methods:
    returnType: map
    signatures: [SITE.Data]
---

Use the `Data` method on a `Site` object to access data within the `data` directory, or within any directory [mounted] to the `data` directory. Supported data formats include JSON, TOML, YAML, and XML.

> [!note]
> Although Hugo can unmarshal CSV files with the [`transform.Unmarshal`] function, do not place CSV files in the `data` directory. You cannot access data within CSV files using this method.

Consider this `data` directory:

```text
data/
├── books/
│   ├── fiction.yaml
│   └── nonfiction.yaml
├── films.json
├── paintings.xml
└── sculptures.toml
```

And these data files:

```yaml {file="data/books/fiction.yaml"}
- title: The Hunchback of Notre Dame
  author: Victor Hugo
  isbn: 978-0140443530
- title: Les Misérables
  author: Victor Hugo
  isbn: 978-0451419439
```

```yaml {file="data/books/nonfiction.yaml"}
- title: The Ancien Régime and the Revolution
  author: Alexis de Tocqueville
  isbn: 978-0141441641
- title: Interpreting the French Revolution
  author: François Furet
  isbn: 978-0521280495
```

Access the data by [chaining](g) the [identifiers](g):

```go-html-template
{{ range $category, $books := .Site.Data.books }}
  <p>{{ $category | title }}</p>
  <ul>
    {{ range $books }}
      <li>{{ .title }} ({{ .isbn }})</li>
    {{ end }}
  </ul>
{{ end }}
```

Hugo renders this to:

```html
<p>Fiction</p>
<ul>
  <li>The Hunchback of Notre Dame (978-0140443530)</li>
  <li>Les Misérables (978-0451419439)</li>
</ul>
<p>Nonfiction</p>
<ul>
  <li>The Ancien Régime and the Revolution (978-0141441641)</li>
  <li>Interpreting the French Revolution (978-0521280495)</li>
</ul>
```

To limit the listing to fiction, and sort by title:

```go-html-template
<ul>
  {{ range sort .Site.Data.books.fiction "title" }}
    <li>{{ .title }} ({{ .author }})</li>
  {{ end }}
</ul>
```

To find a fiction book by ISBN:

```go-html-template
{{ range where .Site.Data.books.fiction "isbn" "978-0140443530" }}
  <li>{{ .title }} ({{ .author }})</li>
{{ end }}
```

In the template examples above, each of the keys is a valid identifier. For example, none of the keys contains a hyphen. To access a key that is not a valid identifier, use the [`index`] function. For example:

```go-html-template
{{ index .Site.Data.books "historical-fiction" }}
```

[`index`]: /functions/collections/indexfunction/
[`transform.Unmarshal`]: /functions/transform/unmarshal/
[mounted]: /configuration/module/#mounts
