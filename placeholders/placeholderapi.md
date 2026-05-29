# PlaceholderAPI

Runway supports PlaceholderAPI when the plugin is installed and enabled before Runway finishes loading.

{% hint style="info" %}
Inside Runway text, use `<papi:player_name>`. In other PlaceholderAPI-compatible plugins, use `%runway_placeholder%`.
{% endhint %}

## Using PlaceholderAPI Inside Runway Text

Use the `<papi:...>` tag without percent signs:

```text
$<green>Hello <papi:player_name>
```

The long alias also works:

```text
$<placeholderapi:player_name>
```

## Nested PlaceholderAPI Output

Runway parses PlaceholderAPI output again. That means a PlaceholderAPI value may return another PlaceholderAPI placeholder or a Runway tag.

Example:

```text
$<papi:some_custom_placeholder>
```

If that placeholder returns `<smallcaps>RunwayMC</smallcaps>`, Runway parses the small caps tag.

## Runway As A PlaceholderAPI Expansion

Runway also registers its own PlaceholderAPI expansion:

```text
%runway_<placeholder>%
```

For this custom placeholder:

```yaml
text-placeholders:
  server_name: "RunwayMC"
```

Use this in PlaceholderAPI-compatible plugins:

```text
%runway_server_name%
```

The same final name is used when the placeholder comes from a prefixed group:

```yaml
prefix: server
text-placeholders:
  name: "RunwayMC"
```

PlaceholderAPI syntax:

```text
%runway_server_name%
```

## Quick Comparison

| Context | Syntax |
| --- | --- |
| Runway parsing text directly | `<papi:player_name>` |
| Long Runway alias | `<placeholderapi:player_name>` |
| Another plugin reading PlaceholderAPI expansions | `%runway_server_name%` |
