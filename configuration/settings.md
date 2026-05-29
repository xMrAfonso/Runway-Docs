# Settings

Runway's main file is:

```text
plugins/Runway/settings.yml
```

The exact generated file is the safest source of truth for your installed version. The settings below describe the current server-facing behavior.

## Common Settings

```yaml
debug: false

prefix:
  required: true
  value: $

disableItalics: true

miniPlaceholders:
  refresh-rate: 30
```

## `debug`

Enables extra diagnostic behavior if supported by your build. Keep this off on normal servers unless you are troubleshooting.

## `prefix.required`

Controls whether text must start with the configured prefix before Runway parses it.

When `true`:

```text
$<green>Hello
```

is parsed, but:

```text
<green>Hello
```

is ignored.

When `false`, Runway parses supported text automatically. Use `!$` to skip parsing for one message when the prefix value is `$`.

## `prefix.value`

The marker Runway looks for at the start of text. The default is `$`.

You can change it:

```yaml
prefix:
  required: true
  value: "[mm]"
```

Then messages should start with:

```text
[mm]<gold>Hello
```

## `disableItalics`

When enabled, Runway adds `<!italic>` before parsed text. This is mainly useful for item names and lore, because Minecraft often renders them italic by default.

## `miniPlaceholders.refresh-rate`

Controls how often Runway refreshes MiniPlaceholders audience global placeholders, in seconds.

Use a positive value for cached refreshes:

```yaml
miniPlaceholders:
  refresh-rate: 30
```

Use `0` or a negative value to refresh on every parse. That can be more current, but more expensive.

