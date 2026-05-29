# PlaceholderAPI

Runway supports PlaceholderAPI when the PlaceholderAPI plugin is installed and enabled before Runway finishes loading.

## Using PlaceholderAPI Inside Runway Text

Use the `<papi:...>` tag without percent signs:

```text
$<green>Hello <papi:player_name>
```

This sends `%player_name%` to PlaceholderAPI.

The long alias also works:

```text
$<placeholderapi:player_name>
```

## Nested PlaceholderAPI Output

Runway parses PlaceholderAPI output again, so a PlaceholderAPI value can return another PlaceholderAPI placeholder or Runway tag.

Example:

```text
$<papi:some_custom_placeholder>
```

If that placeholder returns `<smallcaps>RunwayMC</smallcaps>`, Runway parses the small caps tag.

## Runway As A PlaceholderAPI Expansion

When PlaceholderAPI is installed, Runway registers the expansion:

```text
%runway_<placeholder>%
```

Example custom placeholder:

```yaml
text-placeholders:
  server_name: "RunwayMC"
```

Use in PlaceholderAPI-compatible plugins:

```text
%runway_server_name%
```

For a prefixed placeholder:

```yaml
prefix: server
text-placeholders:
  name: "RunwayMC"
```

Use:

```text
%runway_server_name%
```

