# Items And Inventories

Runway can parse item display names and lore from supported item packets.

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

