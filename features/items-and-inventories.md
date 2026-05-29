# Items and Inventories

Runway formats item names and lore from the item packets it can safely read.

{% hint style="info" %}
Minecraft often renders item text in italics by default. `disableItalics: true` keeps formatted item text looking like normal UI text.
{% endhint %}

## What Controls What

| Goal | Setting |
| --- | --- |
| Parse window titles | `listeners.inventory.title.enable` |
| Parse items inside inventory windows | `listeners.inventory.items.enable` |
| Parse individual item update packets | `listeners.items.enable` |
| Remove default item italics | `disableItalics: true` |

Keep `disableItalics: true` if you do not want formatted item names and lore to appear italic by default.

If you want italic text intentionally, add it yourself:

```text
$<italic><gray>Ancient blade
```
