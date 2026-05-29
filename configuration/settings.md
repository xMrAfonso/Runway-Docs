# Settings

Runway's main file is:

<div style="padding: 14px 16px; border: 1px solid #e2e8f0; border-radius: 10px; background: #fbfdff; margin: 12px 0;">
  <code>plugins/Runway/settings.yml</code>
</div>

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

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 12px; margin: 14px 0;">
  <div style="padding: 14px; border: 1px solid #d9e7ff; border-radius: 10px; background: #f7fbff;"><strong><code>prefix.required: true</code></strong><br><span style="color: #526070;">Only text starting with <code>prefix.value</code> is parsed.</span></div>
  <div style="padding: 14px; border: 1px solid #dfe7d9; border-radius: 10px; background: #f8fff7;"><strong><code>prefix.required: false</code></strong><br><span style="color: #526070;">Supported text is parsed automatically unless a listener requires the prefix.</span></div>
  <div style="padding: 14px; border: 1px solid #eadfc7; border-radius: 10px; background: #fffaf0;"><strong><code>prefix.value: "[mm]"</code></strong><br><span style="color: #526070;">Messages start with <code>[mm]</code> instead of <code>$</code>.</span></div>
</div>

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
