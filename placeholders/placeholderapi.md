# PlaceholderAPI

Runway supports PlaceholderAPI when the plugin is installed and enabled before Runway finishes loading.

{% hint style="info" %}
Inside Runway text, use `<papi:player_name>`. In other PlaceholderAPI-compatible plugins, use `%runway_placeholder%`.
{% endhint %}

## Syntax

| Context | Syntax |
| --- | --- |
| Runway text | `$<green>Hello <papi:player_name>` |
| Long Runway alias | `<placeholderapi:player_name>` |
| Another plugin reading PlaceholderAPI expansions | `%runway_server_name%` |

Runway parses PlaceholderAPI output again, so PlaceholderAPI values may return MiniMessage or Runway tags.

## Runway As A PlaceholderAPI Expansion

Custom Runway placeholders can be used in other PlaceholderAPI-compatible plugins:

| Runway placeholder setup | PlaceholderAPI syntax |
| --- | --- |
| `server_name` | `%runway_server_name%` |
| `prefix: server` and `name` | `%runway_server_name%` |

## Checks When It Is Blank

| Check | Why it matters |
| --- | --- |
| PlaceholderAPI is installed | Runway only registers this support when PlaceholderAPI is present. |
| The expansion is installed | PlaceholderAPI placeholders usually come from separate expansions. |
| Player context exists | Player placeholders need a receiving player. |
| Syntax matches the context | Use `<papi:...>` inside Runway text and `%runway_...%` in other PlaceholderAPI-compatible plugins. |

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
