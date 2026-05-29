# Settings

Runway's main file is:

```text
plugins/Runway/settings.yml
```

The generated file is the safest source of truth for your installed version. The settings below are the ones you are most likely to change.

{% hint style="info" %}
After editing `settings.yml`, run `/runway reload`.
{% endhint %}

## Setting Reference

| Setting | Default | What it controls |
| --- | --- | --- |
| `debug` | `false` | Extra diagnostic behavior, when supported by the build. |
| `prefix.required` | `true` | Whether text must start with the prefix before Runway parses it. |
| `prefix.value` | `$` | The marker Runway removes before parsing. |
| `disableItalics` | `true` | Whether Runway adds `<!italic>` before parsed text. |
| `miniPlaceholders.refresh-rate` | `30` | How often cached MiniPlaceholders audience globals refresh, in seconds. |

## Prefix Behavior

| Setup | Result |
| --- | --- |
| `prefix.required: true` | Only text starting with `prefix.value` is parsed. |
| `prefix.required: false` | Supported text is parsed automatically unless a listener requires the prefix. |
| `prefix.value: "[mm]"` | Messages start with `[mm]` instead of `$`. |

## `debug`

Enables extra diagnostic behavior if supported by your build. Keep this off on normal servers unless you are troubleshooting.

## `prefix.required`

When `prefix.required` is `true`, this is parsed:

```text
$<green>Hello
```

This is ignored:

```text
<green>Hello
```

When `prefix.required` is `false`, use `!$` to skip parsing for one message when the prefix is `$`.

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

Use `0` or a negative value to refresh on every parse. That can be more current, but more expensive.

{% hint style="warning" %}
Refreshing MiniPlaceholders on every parse can be useful while testing, but busy servers should usually keep a positive refresh rate.
{% endhint %}
