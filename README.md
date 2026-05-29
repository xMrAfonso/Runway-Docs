# Runway Documentation

Runway brings MiniMessage formatting to text that other Minecraft plugins send as plain text.

[Install Runway](getting-started/installation.md) | [Run a test](getting-started/first-formatting-test.md) | [See examples](examples/README.md)

Use it when another plugin gives you a plain text box, but you want gradients, hover text, PlaceholderAPI values, MiniPlaceholders values, or reusable server-wide tags.

{% hint style="info" %}
The usual workflow is simple: write MiniMessage in another plugin's config, add the Runway prefix if needed, then let Runway format the outgoing packet.
{% endhint %}

## What Runway Can Format

| Area | Examples |
| --- | --- |
| Messages | Chat, system messages, plugin messages |
| HUD | Action bars, boss bars, titles |
| Menus | Tab list text, inventory titles |
| Items | Display names, lore, item packets |
| Dialogs | Text, buttons, inputs, dialog items |
| Names | Text displays, nameplates, tab names |

## Fast Example

With the default prefix, write this in another plugin message:

```text
$<gradient:#0050ff:#00d4ff>Welcome to <server_name></gradient>
```

Runway removes `$`, parses the MiniMessage tags, resolves `<server_name>` if you configured it, and sends the formatted result to the player.

{% hint style="success" %}
Use `/runway parse <text>` when you want to test formatting before editing a larger config.
{% endhint %}

## Files Created By Runway

After the first startup, Runway uses:

| File | Used for |
| --- | --- |
| `plugins/Runway/settings.yml` | Prefixes, listeners, item italics, MiniPlaceholders refreshes |
| `plugins/Runway/lang.yml` | Runway command messages |
| `plugins/Runway/placeholders/*.yml` | Custom placeholder groups |

Older `config.yml` and `placeholders.yml` files are migrated automatically when possible.

## Start Here

| Goal | Page |
| --- | --- |
| Install the plugin | [Installation](getting-started/installation.md) |
| Check formatting | [First Formatting Test](getting-started/first-formatting-test.md) |
| Understand prefixes | [How Runway Parses Text](getting-started/how-runway-parses-text.md) |
| Choose text locations | [Listeners](configuration/listeners.md) |
| Copy a setup | [Configuration Setups](examples/configuration-setups.md) |
