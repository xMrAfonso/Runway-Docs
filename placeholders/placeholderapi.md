# PlaceholderAPI

Runway supports PlaceholderAPI when the plugin is installed and enabled before Runway finishes loading.

{% hint style="info" %}
Inside Runway text, use `<papi:player_name>`. In other PlaceholderAPI-compatible plugins, use `%runway_placeholder%`.
{% endhint %}

## Syntax

- Runway text: `$<green>Hello <papi:player_name>`
- Long Runway alias: `<placeholderapi:player_name>`
- Other PlaceholderAPI-compatible plugins: `%runway_server_name%`

Runway parses PlaceholderAPI output again, so PlaceholderAPI values may return MiniMessage or Runway tags.

## Runway As A PlaceholderAPI Expansion

Custom Runway placeholders can be used in other PlaceholderAPI-compatible plugins:

- `server_name` becomes `%runway_server_name%`.
- `prefix: server` with `name` also becomes `%runway_server_name%`.

## Checks When It Is Blank

- PlaceholderAPI must be installed before Runway can register support.
- The expansion for that placeholder must be installed.
- Player placeholders need a receiving player.
- Syntax depends on the context: use `<papi:...>` inside Runway text and `%runway_...%` in other PlaceholderAPI-compatible plugins.

## Setup Examples

### Rank Greeting

```yaml
placeholders:
  rank_greeting:
    type: MATCH
    input: "<papi:luckperms_primary_group_name>"
    case:
      - comparison: "owner"
        output: "<red>Welcome back, Owner</red>"
      - comparison: "vip"
        output: "<gold>Welcome back, VIP</gold>"
    default: "<gray>Welcome back</gray>"
```

Usage:

```text
$<rank_greeting> <papi:player_name>!
```

### Online Count Status

```yaml
placeholders:
  online_status:
    type: SWITCH
    input: "<papi:server_online>"
    case:
      - comparison: "> 100"
        output: "<green>Busy server</green>"
      - comparison: "< 10"
        output: "<yellow>Quiet server</yellow>"
    default: "<aqua>Active server</aqua>"
```

If `<papi:server_online>` returns `150`, Runway evaluates `150 > 100`.
