---
# Copyright (c) 2013–2025 The Hugo Authors.
# The Hugo logos are copyright (c) Steve Francia 2013–2025.
# The Hugo Gopher is based on an original work by Renée French.
#
# Documentation licensed under the Apache License, Version 2.0.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/gohugoio/hugoDocs/blob/master/content/LICENSE.md

title: time.Format
description: Returns the given date/time as a formatted and localized string.
categories: []
keywords: []
params:
  functions_and_methods:
    aliases: [dateFormat]
    returnType: string
    signatures: [time.Format LAYOUT INPUT]
aliases: [/functions/dateformat]
---

Use the `time.Format` function with `time.Time` values:

```go-html-template
{{ $t := time.AsTime "2023-10-15T13:18:50-07:00" }}
{{ time.Format "2 Jan 2006" $t }} → 15 Oct 2023
```

Or use `time.Format` with a parsable string representation of a date/time value:

```go-html-template
{{ $t := "15 Oct 2023" }}
{{ time.Format "January 2, 2006" $t }} → October 15, 2023
```

Examples of parsable string representations:

{{% include "/_common/parsable-date-time-strings.md" %}}

To override the default time zone, set the [`timeZone`] in your site configuration. The order of precedence for determining the time zone is:

1. The time zone offset in the date/time string
1. The time zone specified in your site configuration
1. The `Etc/UTC` time zone

[`timeZone`]: /configuration/all/#timezone

## Layout string

{{% include "/_common/time-layout-string.md" %}}

## Localization

Use the `time.Format` function to localize `time.Time` values for the current language and region.

{{% include "/_common/functions/locales.md" %}}

Use the layout string as described above, or one of the tokens below. For example:

```go-html-template
{{ .Date | time.Format ":date_medium" }} → Jan 27, 2023
```

Localized to en-US:

Token|Result
:--|:--
`:date_full`|`Friday, January 27, 2023`
`:date_long`|`January 27, 2023`
`:date_medium`|`Jan 27, 2023`
`:date_short`|`1/27/23`
`:time_full`|`11:44:58 pm Pacific Standard Time`
`:time_long`|`11:44:58 pm PST`
`:time_medium`|`11:44:58 pm`
`:time_short`|`11:44 pm`

Localized to de-DE:

Token|Result
:--|:--
`:date_full`|`Freitag, 27. Januar 2023`
`:date_long`|`27. Januar 2023`
`:date_medium`|`27.01.2023`
`:date_short`|`27.01.23`
`:time_full`|`23:44:58 Nordamerikanische Westküsten-Normalzeit`
`:time_long`|`23:44:58 PST`
`:time_medium`|`23:44:58`
`:time_short`|`23:44`
