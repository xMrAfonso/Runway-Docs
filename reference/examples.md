# Examples

Use these as copyable starting points, then change names, colors, and PlaceholderAPI keys to match your server.

{% hint style="info" %}
Quote YAML values that contain MiniMessage tags, hex colors, URLs, or colons.
{% endhint %}

## Server Branding

`plugins/Runway/placeholders/global.yml`

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

## Rank Greeting With PlaceholderAPI

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

<details>
<summary>What this example does</summary>

It reads the player's primary LuckPerms group through PlaceholderAPI, compares the exact group name, and returns the first matching greeting. If no case matches, it uses the `default` value.

</details>

## Online Count Status

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

Usage:

```text
$Status: <online_status>
```

<details>
<summary>What this example does</summary>

It combines the PlaceholderAPI online count with each comparison. If the server has `150` players online, Runway evaluates `150 > 100` for the first case.

</details>

## Random Tips

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
