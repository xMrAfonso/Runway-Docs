# Message Recipes

These examples use the default `$` prefix.

{% hint style="info" %}
Use the [MiniMessage Web UI](https://webui.advntr.dev/) to preview colors, gradients, hover text, and click events.
{% endhint %}

## Welcome Message

```text
$<gradient:#0050ff:#00d4ff>Welcome to <server_name></gradient>
```

## Store Link

```text
$<click:open_url:'https://store.example.com'><hover:show_text:'<gray>Open the store'><aqua>store.example.com</aqua></hover></click>
```

## Lobby Button

```text
$<hover:show_text:'<gray>Click to join'><click:run_command:'/server lobby'><green>Lobby</green></click></hover>
```

## Action Bar Notice

```text
$<actionbar><green>Quest updated!</green></actionbar>
```

## Item Lore Line

```text
$<!italic><gray>Forged below the old city.
```

## YAML Version

```yaml
message: "$<gradient:#0050ff:#00d4ff>Hello</gradient>"
```
