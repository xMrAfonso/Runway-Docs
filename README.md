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

Use it when another plugin gives you a plain text box, but you want gradients, hover text, PlaceholderAPI values, MiniPlaceholders values, or reusable server-wide tags.

{% hint style="info" %}
The usual workflow is simple: write MiniMessage in another plugin's config, add the Runway prefix if needed, then let Runway format the outgoing packet.
{% endhint %}

## What Runway Can Format

| Area | What Runway can touch |
| --- | --- |
| Messages | Player chat, system messages, plugin messages |
| HUD | Action bars, boss bars, titles, subtitles |
| Menus | Tab list header/footer, inventory titles |
| Items | Display names, lore, item packets |
| Dialogs | Text, buttons, inputs, dialog items |
| Names | Text displays, nameplates, tab list names, scoreboard team names |

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

| If you want to... | Go here |
| --- | --- |
| Install the plugin | [Installation](getting-started/installation.md) |
| Check that formatting works | [First Formatting Test](getting-started/first-formatting-test.md) |
| Understand prefixes | [How Runway Parses Text](getting-started/how-runway-parses-text.md) |
| Choose what gets parsed | [Listeners](configuration/listeners.md) |
