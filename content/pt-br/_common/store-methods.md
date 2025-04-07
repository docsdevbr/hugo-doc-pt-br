---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

source_url: https://github.com/gohugoio/hugoDocs/blob/master/content/en/_common/store-methods.md
revision: b6cae5cbc662fa92a00d123bd758fe1205b8a07e
status: ready

_comment: Do not remove front matter.
---

## Métodos

### Set

Define o valor da chave fornecida.

```go-html-template
{{ .Store.Set "greeting" "Olá" }}
```

### Get

Obtém o valor da chave fornecida.

```go-html-template
{{ .Store.Set "greeting" "Olá" }}
{{ .Store.Get "greeting" }} → Olá
```

### Add

Adiciona o valor fornecido aos valores existentes da chave fornecida.

Para valores únicos, `Add` aceita valores que suportam o operador `+` do Go.
Se o primeiro `Add` para uma chave for um array ou slice, as adições seguintes
serão anexadas a essa lista.

```go-html-template
{{ .Store.Set "greeting" "Olá" }}
{{ .Store.Add "greeting" "Boas-vindas" }}
{{ .Store.Get "greeting" }} → OláBoas-vindas
```

```go-html-template
{{ .Store.Set "total" 3 }}
{{ .Store.Add "total" 7 }}
{{ .Store.Get "total" }} → 10
```

```go-html-template
{{ .Store.Set "greetings" (slice "Olá") }}
{{ .Store.Add "greetings" (slice "Boas-vindas" "Saúde") }}
{{ .Store.Get "greetings" }} → [Olá Boas-vindas Saúde]
```

### SetInMap

Recebe uma `key`, `mapKey` e `value` e adiciona um mapa de `mapKey` e `value` à `key` fornecida.

```go-html-template
{{ .Store.SetInMap "greetings" "portuguese" "Olá" }}
{{ .Store.SetInMap "greetings" "french" "Bonjour" }}
{{ .Store.Get "greetings" }} → map[portuguese:Olá french:Bonjour]
  ```

### DeleteInMap

Recebe uma `key` e `mapKey` e remove o mapa de `mapKey` da `key` fornecida.

```go-html-template
{{ .Store.SetInMap "greetings" "portuguese" "Olá" }}
{{ .Store.SetInMap "greetings" "french" "Bonjour" }}
{{ .Store.DeleteInMap "greetings" "portuguese" }}
{{ .Store.Get "greetings" }} → map[french:Bonjour]
```

### GetSortedMapValues

Retorna um array de valores de `key` ordenados por `mapKey`.

```go-html-template
{{ .Store.SetInMap "greetings" "portuguese" "Olá" }}
{{ .Store.SetInMap "greetings" "french" "Bonjour" }}
{{ .Store.GetSortedMapValues "greetings" }} → [Olá Bonjour]
```

### Delete

Remove a chave fornecida.

```go-html-template
{{ .Store.Set "greeting" "Olá" }}
{{ .Store.Delete "greeting" }}
```
