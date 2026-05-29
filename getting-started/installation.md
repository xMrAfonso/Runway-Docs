# Installation

{% hint style="info" %}
Runway is a Paper plugin. Install it on the server, not on the client.
{% endhint %}

## Requirements

| Requirement | Notes |
| --- | --- |
| Paper `1.21+` | Use the version supported by your Runway build. |
| Java `21+` | Or the Java version required by your Paper build. |
| PlaceholderAPI | Optional. Needed for `<papi:...>` tags. |
| MiniPlaceholders | Optional. Needed for MiniPlaceholders tags. |

## Install Runway

1. Stop your server.
2. Put the Runway jar in your server's `plugins` folder.
3. Install PlaceholderAPI or MiniPlaceholders too if you want to use their placeholders.
4. Start the server.
5. Open `plugins/Runway/settings.yml`.
6. Adjust the prefix and listeners.
7. Run `/runway reload` after configuration changes.

## Check That It Loaded

On startup, Runway logs that it enabled. If PlaceholderAPI or MiniPlaceholders are present, it also logs support for them.

{% hint style="warning" %}
If a message is not changing, check the matching listener before changing the message itself.
{% endhint %}

If the server does not start, check:

- The server is Paper, not Spigot.
- The Minecraft version is supported by your Runway build.
- The Java version matches your Paper and Runway build.
- There are no broken YAML files in `plugins/Runway`.
