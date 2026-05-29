# Placeholder Types

Typed placeholders go under `placeholders`. Use them when plain text replacements are not enough.

| Type | Best for |
| --- | --- |
| `TEXT` | Static or formatted reusable text |
| `NUMBER` | Numeric values |
| `RANDOM` | Rotating tips, messages, or labels |
| `CONDITIONAL` | Permission, state, or boolean checks |
| `MATCH` | Exact text comparisons, such as locale or rank |
| `SWITCH` | Numeric or boolean comparisons |

## TEXT

Inserts MiniMessage text.

```yaml
placeholders:
  server_name:
    type: TEXT
    value: "RunwayMC"
```

Tag:

```text
<server_name>
```

## NUMBER

Inserts a number.

```yaml
placeholders:
  max_players:
    type: NUMBER
    value: 100.0
```

## RANDOM

Chooses a random value from a list.

```yaml
placeholders:
  tip:
    type: RANDOM
    value:
      - "<green>Use /spawn to return home."
      - "<yellow>Join the Discord for updates."
      - "<aqua>Check /shop for rewards."
```

An empty list returns empty text.

## CONDITIONAL

Chooses output from a boolean expression.

```yaml
placeholders:
  donor_badge:
    type: CONDITIONAL
    condition: "<vip_enabled> == true"
    if-true: "<gold>VIP</gold>"
    else: "<gray>Member</gray>"
```

`else` is optional. Without it, false outputs empty text.

## MATCH

Compares processed text and uses the first exact match.

```yaml
placeholders:
  greeting:
    type: MATCH
    input: "fr_FR"
    case:
      - comparison: "en_US"
        output: "Hello!"
      - comparison: "es_ES"
        output: "Hola!"
      - comparison: "fr_FR"
        output: "Bonjour!"
    default: "Hello!"
```

## SWITCH

Evaluates numeric or boolean expressions by combining `input` with each comparison.

```yaml
placeholders:
  online_status:
    type: SWITCH
    input: "150"
    case:
      - comparison: "> 100"
        output: "<green>Busy</green>"
      - comparison: "< 20"
        output: "<yellow>Quiet</yellow>"
    default: "<aqua>Normal</aqua>"
```

If `input` is `150`, Runway evaluates `150 > 100`.

PlaceholderAPI examples are grouped on the [PlaceholderAPI](placeholderapi.md) page.

## `sanitized`

Typed placeholders are blocked in sanitized chat unless you opt them in:

```yaml
placeholders:
  server_name:
    type: TEXT
    sanitized: true
    value: "RunwayMC"
```

This matters for player-written chat. Leave it off for placeholders that should only be used by trusted configs.

{% hint style="warning" %}
Only mark a placeholder as `sanitized: true` when it is safe for player-written chat contexts.
{% endhint %}
