# Runway Documentation

Runway brings MiniMessage formatting to text that other Minecraft plugins send as plain text.

Quick links:

- [Install Runway](getting-started/installation.md)
- [Run a test](getting-started/first-formatting-test.md)
- [See examples](examples/README.md)

Use it when another plugin gives you a plain text box, but you want gradients, hover text, PlaceholderAPI values, MiniPlaceholders values, or reusable server-wide tags.

{% hint style="info" %}
The usual workflow is simple: write MiniMessage in another plugin's config, add the Runway prefix if needed, then let Runway format the outgoing packet.
{% endhint %}

## What Runway Can Format

- **Messages:** chat, system messages, plugin messages
- **HUD:** action bars, boss bars, titles
- **Menus:** tab list text, inventory titles
- **Items:** display names, lore, item packets
- **Dialogs:** text, buttons, inputs, dialog items
- **Names:** text displays, nameplates, tab names

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

- `plugins/Runway/settings.yml` for prefixes, listeners, item italics, and MiniPlaceholders refreshes.
- `plugins/Runway/lang.yml` for Runway command messages.
- `plugins/Runway/placeholders/*.yml` for custom placeholder groups.

Older `config.yml` and `placeholders.yml` files are migrated automatically when possible.

## Start Here

- [Installation](getting-started/installation.md) for requirements and setup.
- [First Formatting Test](getting-started/first-formatting-test.md) to check formatting.
- [How Runway Parses Text](getting-started/how-runway-parses-text.md) to understand prefixes.
- [Listeners](configuration/listeners.md) to choose text locations.
- [Configuration Setups](examples/configuration-setups.md) for copyable recipes.
