<div style="padding: 32px 28px; border: 1px solid #d9e7ff; border-radius: 14px; background: linear-gradient(135deg, #f7fbff 0%, #eef6ff 48%, #f8fff9 100%);">
  <p style="margin: 0 0 8px; font-size: 13px; font-weight: 700; letter-spacing: .08em; text-transform: uppercase; color: #1f6feb;">Runway for Paper servers</p>
  <h1 style="margin: 0 0 12px; font-size: 36px; line-height: 1.1;">MiniMessage formatting where plugins only give you plain text</h1>
  <p style="margin: 0 0 22px; max-width: 760px; color: #405268; font-size: 16px;">Runway reads outgoing text packets and turns marked strings into Adventure components before players receive them.</p>
  <p style="margin: 0;">
    <a href="getting-started/installation.md" style="display: inline-block; padding: 10px 16px; margin: 0 8px 8px 0; border-radius: 8px; background: #1f6feb; color: #ffffff; font-weight: 700; text-decoration: none;">Install Runway</a>
    <a href="getting-started/first-formatting-test.md" style="display: inline-block; padding: 10px 16px; margin: 0 8px 8px 0; border-radius: 8px; background: #ffffff; color: #1f6feb; border: 1px solid #b9d3ff; font-weight: 700; text-decoration: none;">Run a test</a>
    <a href="reference/examples.md" style="display: inline-block; padding: 10px 16px; margin: 0 0 8px 0; border-radius: 8px; background: #ffffff; color: #24503a; border: 1px solid #bfe4ce; font-weight: 700; text-decoration: none;">See examples</a>
  </p>
</div>

Use it when another plugin gives you a plain text box, but you want gradients, hover text, PlaceholderAPI values, MiniPlaceholders values, or reusable server-wide tags.

{% hint style="info" %}
The usual workflow is simple: write MiniMessage in another plugin's config, add the Runway prefix if needed, then let Runway format the outgoing packet.
{% endhint %}

## What Runway Can Format

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(190px, 1fr)); gap: 12px; margin: 16px 0 24px;">
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>Messages</strong><br><span style="color: #526070;">Chat, system messages, plugin messages</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>HUD</strong><br><span style="color: #526070;">Action bars, boss bars, titles</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>Menus</strong><br><span style="color: #526070;">Tab list text, inventory titles</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>Items</strong><br><span style="color: #526070;">Display names, lore, item packets</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>Dialogs</strong><br><span style="color: #526070;">Text, buttons, inputs, dialog items</span></div>
  <div style="padding: 14px; border: 1px solid #e2e8f0; border-radius: 10px; background: #ffffff;"><strong>Names</strong><br><span style="color: #526070;">Text displays, nameplates, tab names</span></div>
</div>

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

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin-top: 14px;">
  <a href="getting-started/installation.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Install the plugin</strong><br><span style="color: #526070;">Requirements and setup steps</span></a>
  <a href="getting-started/first-formatting-test.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Check formatting</strong><br><span style="color: #526070;">Run the parse command and test another plugin</span></a>
  <a href="getting-started/how-runway-parses-text.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Understand prefixes</strong><br><span style="color: #526070;">Learn when Runway parses or ignores text</span></a>
  <a href="configuration/listeners.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Choose text locations</strong><br><span style="color: #526070;">Enable only the listeners you need</span></a>
</div>
