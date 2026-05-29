# Listeners

Listeners control which outgoing text locations Runway is allowed to edit.

{% hint style="info" %}
Turn on the locations you want Runway to touch and leave the rest alone.
{% endhint %}

## Common Listener Options

- `enable`: turns that text location on or off.
- `require-prefix`: requires the configured prefix for this listener when global prefix mode is disabled.
- `sanitize`: chat-only. Limits what player-written chat can resolve.

If `prefix.required` is enabled globally, every listener requires the prefix regardless of its own `require-prefix` value.

## Example

This setup parses most text automatically, but still requires `$` for item update packets:

```yaml
prefix:
  required: false
  value: $

listeners:
  items:
    require-prefix: true
```

## Available Listeners

- `chat`: player chat packets. Also supports `sanitize`.
- `systemMessages`: system and plugin messages. Common for plugin announcements.
- `actionbar`: short action bar text.
- `bossbar`: boss bar titles when they are created or updated.
- `tablist`: tab list header and footer. This does not cover player names.
- `titles`: title and subtitle packets.
- `dialogs`: dialog text, inputs, buttons, and item descriptions. See [Dialogs](../features/dialogs.md).
- `entityText`: text displays and nameplate components.
- `playerNames`: tab list and scoreboard team names.
- `inventory.title`: inventory window titles.
- `inventory.items`: item names and lore in open inventory windows.
- `items`: individual item update packets outside inventory windows.

Some older generated files may have different listener names. Keep the format your installed version generated unless you are migrating with a newer Runway release.
