# Listeners

Listeners control which outgoing text locations Runway is allowed to edit.

<div style="padding: 16px 18px; border: 1px solid #d9e7ff; border-radius: 12px; background: #f7fbff;">
  <strong>Rule of thumb:</strong>
  <span style="color: #526070;">turn on the locations you want Runway to touch and leave the rest alone.</span>
</div>

## Common Listener Options

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(190px, 1fr)); gap: 12px; margin: 14px 0;">
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong><code>enable</code></strong><br><span style="color: #526070;">Turns that text location on or off.</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong><code>require-prefix</code></strong><br><span style="color: #526070;">Requires the configured prefix for this listener when global prefix mode is disabled.</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong><code>sanitize</code></strong><br><span style="color: #526070;">Chat-only. Limits what player-written chat can resolve.</span></div>
</div>

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

| Listener | Text affected | Notes |
| --- | --- |
| `chat` | Player chat packets | Also supports `sanitize`. |
| `systemMessages` | System and plugin messages | Common for plugin announcements. |
| `actionbar` | Action bar text | Short HUD messages. |
| `bossbar` | Boss bar titles | Applies when titles are created or updated. |
| `tablist` | Tab list header and footer | Does not cover player names. |
| `titles` | Titles and subtitles | Full-screen title packets. |
| `dialogs` | Dialog text, inputs, buttons, and item descriptions | See [Dialogs](../features/dialogs.md). |
| `entityText` | Text displays and nameplate components | Entity metadata components. |
| `playerNames` | Tab list and scoreboard team names | Name-related packets. |
| `inventory.title` | Inventory window titles | Menu titles. |
| `inventory.items` | Item names and lore in inventory windows | Items inside open inventories. |
| `items` | Individual item update packets | Item packets outside inventory windows. |

Some older generated files may have different listener names. Keep the format your installed version generated unless you are migrating with a newer Runway release.
