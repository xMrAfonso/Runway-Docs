<div align="center">
  <h1>Runway Documentation</h1>
  <p><strong>MiniMessage formatting for text that other Minecraft plugins send as plain text.</strong></p>
  <p>
    <a href="getting-started/installation.md">Install</a>
    &nbsp;|&nbsp;
    <a href="getting-started/first-formatting-test.md">First test</a>
    &nbsp;|&nbsp;
    <a href="configuration/settings.md">Configure</a>
    &nbsp;|&nbsp;
    <a href="reference/examples.md">Examples</a>
  </p>
</div>

Runway lets server owners use MiniMessage formatting in text sent by other plugins. It works by reading outgoing server packets and converting marked text into Adventure components before the player receives it.

Use Runway when you want gradients, hover text, colors, PlaceholderAPI values, MiniPlaceholders values, or reusable custom placeholders in places where another plugin only gives you plain text configuration.

{% hint style="info" %}
If a plugin lets you configure plain text, Runway can often turn that text into rich Adventure components before it reaches the player.
{% endhint %}

## What Runway Can Format

| Area | Examples |
| --- | --- |
| Chat and messages | Player chat, system messages, plugin messages |
| HUD text | Action bars, boss bars, titles, subtitles |
| Server UI | Tab list header and footer, inventory titles |
| Items | Display names, lore, item packets |
| Dialogs | Text, buttons, inputs, dialog items |
| Entities and names | Text displays, nameplates, tab list names, scoreboard team names |

## Fast Example

With the default prefix set to `$`, write this in another plugin message:

```text
$<gradient:#0050ff:#00d4ff>Welcome to <server_name></gradient>
```

Runway removes the `$`, parses the MiniMessage tags, resolves `<server_name>` if you configured it, and sends the formatted result to the player.

{% hint style="success" %}
Use `/runway parse <text>` in game when you want to preview formatting before putting it into another plugin's config.
{% endhint %}

## Files Created By Runway

After the first startup, Runway uses:

| File | Purpose |
| --- | --- |
| `plugins/Runway/settings.yml` | Main behavior, prefix, listeners, MiniPlaceholders refresh rate |
| `plugins/Runway/lang.yml` | Command feedback messages |
| `plugins/Runway/placeholders/*.yml` | Custom placeholder groups |

Older `config.yml` and `placeholders.yml` files are migrated automatically when possible.

## Start Here

1. [Install Runway](getting-started/installation.md)
2. [Run your first formatting test](getting-started/first-formatting-test.md)
3. [Learn how Runway decides what to parse](getting-started/how-runway-parses-text.md)
4. [Configure listeners](configuration/listeners.md)
