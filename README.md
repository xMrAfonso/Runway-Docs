# Runway Documentation

Runway lets server owners use MiniMessage formatting in text sent by other plugins. It works by reading outgoing server packets and converting marked text into Adventure components before the player receives it.

Use Runway when you want gradients, hover text, colors, PlaceholderAPI values, MiniPlaceholders values, or reusable custom placeholders in places where another plugin only gives you plain text configuration.

## What Runway Can Format

Runway can format:

- Player chat
- System and plugin messages
- Action bars
- Boss bars
- Titles and subtitles
- Tab list header and footer
- Inventory titles
- Item names and lore
- Dialog text, buttons, inputs, and dialog items
- Entity text, such as text displays and nameplates
- Player names from tab list and scoreboard team packets

## Fast Example

With the default prefix set to `$`, write this in another plugin message:

```text
$<gradient:#0050ff:#00d4ff>Welcome to <server_name></gradient>
```

Runway removes the `$`, parses the MiniMessage tags, resolves `<server_name>` if you configured it, and sends the formatted result to the player.

## Files Created By Runway

After the first startup, Runway uses:

- `plugins/Runway/settings.yml` for main behavior.
- `plugins/Runway/lang.yml` for command messages.
- `plugins/Runway/placeholders/*.yml` for custom placeholder groups.

Older `config.yml` and `placeholders.yml` files are migrated automatically when possible.

