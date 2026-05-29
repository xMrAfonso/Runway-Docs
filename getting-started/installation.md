# Installation

<div style="padding: 18px 20px; border: 1px solid #d9e7ff; border-radius: 12px; background: #f7fbff;">
  <strong>Install Runway on the server.</strong>
  <p style="margin: 6px 0 0; color: #526070;">Runway is a Paper plugin. Players do not need to install anything.</p>
</div>

## Requirements

| Requirement | Notes |
| --- | --- |
| Paper `1.21+` | Use the version supported by your Runway build. |
| Java `21+` | Or the Java version required by your Paper build. |
| PlaceholderAPI | Optional. Needed for `<papi:...>` tags. |
| MiniPlaceholders | Optional. Needed for MiniPlaceholders tags. |

## Install Runway

<div style="display: grid; gap: 10px; margin: 14px 0;">
  <div style="padding: 12px 14px; border-left: 4px solid #1f6feb; background: #f7fbff;"><strong>1. Stop the server</strong><br><span style="color: #526070;">Do plugin changes while the server is offline.</span></div>
  <div style="padding: 12px 14px; border-left: 4px solid #1f6feb; background: #f7fbff;"><strong>2. Add the jar</strong><br><span style="color: #526070;">Put the Runway jar in your server's <code>plugins</code> folder.</span></div>
  <div style="padding: 12px 14px; border-left: 4px solid #1f6feb; background: #f7fbff;"><strong>3. Add optional placeholder plugins</strong><br><span style="color: #526070;">Install PlaceholderAPI or MiniPlaceholders if you plan to use them.</span></div>
  <div style="padding: 12px 14px; border-left: 4px solid #1f6feb; background: #f7fbff;"><strong>4. Start and configure</strong><br><span style="color: #526070;">Open <code>plugins/Runway/settings.yml</code>, adjust listeners, then run <code>/runway reload</code>.</span></div>
</div>

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
