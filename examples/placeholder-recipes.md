# Placeholder Recipes

Put these files in `plugins/Runway/placeholders/`, then run `/runway reload`.

## Global Server Text

`global.yml`

```yaml
text-placeholders:
  server_name: "<gradient:#0050ff:#00d4ff>RunwayMC</gradient>"
  discord: "<click:open_url:'https://discord.example.com'><hover:show_text:'<gray>Click to open'><aqua>discord.example.com</aqua></hover></click>"
```

Usage:

```text
$Welcome to <server_name>
$Join us at <discord>
```

## Prefixed Shop Tags

`shop.yml`

```yaml
prefix: shop

text-placeholders:
  name: "<gold>Runway Store</gold>"
  sale: "<green>25% off this weekend</green>"
```

Usage:

```text
$Visit <shop_name>: <shop_sale>
```

## Random Tips

`tips.yml`

```yaml
placeholders:
  tip:
    type: RANDOM
    value:
      - "<green>Use /spawn to return to spawn."
      - "<aqua>Use /rtp to explore."
      - "<yellow>Vote daily for rewards."
```

Usage:

```text
$Tip: <tip>
```

## Conditional Badge

```yaml
placeholders:
  event_badge:
    type: CONDITIONAL
    condition: "<event_active> == true"
    if-true: "<gold>Event</gold>"
    else: "<gray>Normal</gray>"
```

For PlaceholderAPI-backed placeholders, keep the setup on [PlaceholderAPI](../placeholders/placeholderapi.md).
