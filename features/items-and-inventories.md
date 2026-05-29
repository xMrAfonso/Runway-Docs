# Items And Inventories

Runway can parse item display names and lore from supported item packets.

{% hint style="info" %}
Minecraft often renders item text in italics by default. `disableItalics: true` keeps formatted item text looking like normal UI text.
{% endhint %}

## Settings

```yaml
disableItalics: true

listeners:
  inventory:
    title:
      enable: true
      require-prefix: false
    items:
      enable: true
      require-prefix: false
  items:
    enable: true
    require-prefix: false
```

## Inventory Titles

Inventory titles are controlled by:

```yaml
listeners:
  inventory:
    title:
      enable: true
```

## Inventory Contents

Items sent in inventory windows are controlled by:

```yaml
listeners:
  inventory:
    items:
      enable: true
```

## Item Updates

Individual item update packets are controlled by:

```yaml
listeners:
  items:
    enable: true
```

## Italics

Keep `disableItalics: true` if you do not want formatted item names and lore to appear italic by default.

If you want italic text intentionally, add it yourself:

```text
$<italic><gray>Ancient blade
```

## Listener Map

| Goal | Setting |
| --- | --- |
| Parse window titles | `listeners.inventory.title.enable` |
| Parse items inside inventory windows | `listeners.inventory.items.enable` |
| Parse individual item update packets | `listeners.items.enable` |
| Remove default item italics | `disableItalics: true` |
