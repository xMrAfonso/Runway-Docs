# Placeholder Types

Typed placeholders go under `placeholders`.

```yaml
placeholders:
  example:
    type: TEXT
    sanitized: false
    value: "Hello!"
```

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

Use:

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

An empty random list outputs empty text.

## CONDITIONAL

Chooses output based on a boolean expression.

```yaml
placeholders:
  donor_badge:
    type: CONDITIONAL
    condition: "<papi:luckperms_in_group_vip> == true"
    if-true: "<gold>VIP</gold>"
    else: "<gray>Member</gray>"
```

`else` is optional. Without it, false outputs empty text.

## MATCH

Compares processed text values and picks the first equal case.

```yaml
placeholders:
  greeting:
    type: MATCH
    input: "<papi:player_locale>"
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

Evaluates numeric or boolean expressions by joining `input` and each case comparison.

```yaml
placeholders:
  online_status:
    type: SWITCH
    input: "<papi:server_online>"
    case:
      - comparison: "> 100"
        output: "<green>Busy</green>"
      - comparison: "< 20"
        output: "<yellow>Quiet</yellow>"
    default: "<aqua>Normal</aqua>"
```

If `<papi:server_online>` is `150`, Runway evaluates `150 > 100`.

## `sanitized`

Typed placeholders can opt in to sanitized contexts:

```yaml
placeholders:
  server_name:
    type: TEXT
    sanitized: true
    value: "RunwayMC"
```

When player chat sanitizing is enabled, only sanitized typed placeholders are available in the sanitized part of the message.

{% hint style="warning" %}
Only mark a placeholder as `sanitized: true` when it is safe for player-written chat contexts.
{% endhint %}
