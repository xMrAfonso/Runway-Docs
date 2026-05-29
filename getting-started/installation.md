# Installation

{% hint style="info" %}
Install Runway on the server. Players do not need to install anything.
{% endhint %}

## Requirements

- Paper `1.21+`, or the version supported by your Runway build.
- Java `21+`, or the Java version required by your Paper build.
- PlaceholderAPI, optional. Needed for `<papi:...>` tags.
- MiniPlaceholders, optional. Needed for MiniPlaceholders tags.

## Install Runway

1. Stop the server.
2. Put the Runway jar in your server's `plugins` folder.
3. Install PlaceholderAPI or MiniPlaceholders if you plan to use them.
4. Start the server.
5. Open `plugins/Runway/settings.yml`.
6. Adjust listeners and prefix behavior.
7. Run `/runway reload`.

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
