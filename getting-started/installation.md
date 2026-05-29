# Installation

## Requirements

Runway is a Paper plugin. Use a modern Paper server that matches the Runway release you downloaded. The current plugin metadata targets the Paper `1.21` API.

Recommended:

- Paper `1.21+`
- Java `21+`, or the Java version required by your Paper build
- PlaceholderAPI, optional
- MiniPlaceholders, optional

## Install Runway

1. Stop your server.
2. Put the Runway jar in your server's `plugins` folder.
3. Install PlaceholderAPI or MiniPlaceholders too if you want to use their placeholders.
4. Start the server.
5. Open `plugins/Runway/settings.yml`.
6. Adjust the prefix and listeners.
7. Run `/runway reload` after configuration changes.

## Check That It Loaded

On startup, Runway logs when it enables. If PlaceholderAPI or MiniPlaceholders are installed and enabled, Runway also logs that support for them was enabled.

If the server does not start, check:

- The server is Paper, not Spigot.
- The Minecraft version is supported by your Runway build.
- The Java version matches your Paper and Runway build.
- There are no broken YAML files in `plugins/Runway`.

