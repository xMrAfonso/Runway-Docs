# Supported Text Locations

Use this as a map from visible text to the listener that controls it.

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 10px; margin: 14px 0;">
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Chat</strong><br><code>listeners.chat</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>System messages</strong><br><code>listeners.systemMessages</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Action bars</strong><br><code>listeners.actionbar</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Boss bars</strong><br><code>listeners.bossbar</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Tab list</strong><br><code>listeners.tablist</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Titles</strong><br><code>listeners.titles</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Dialogs</strong><br><code>listeners.dialogs</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Entity text</strong><br><code>listeners.entityText</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Player names</strong><br><code>listeners.playerNames</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Inventory titles</strong><br><code>listeners.inventory.title</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Inventory items</strong><br><code>listeners.inventory.items</code></div>
  <div style="padding: 12px 14px; border: 1px solid #e2e8f0; border-radius: 10px;"><strong>Item updates</strong><br><code>listeners.items</code></div>
</div>

{% hint style="info" %}
If a text location is not changing, check its listener and prefix behavior first.
{% endhint %}

## Notes By Area

| Area | Note |
| --- | --- |
| Chat | See [Chat Formatting and Sanitizing](../formatting/chat-formatting-and-sanitizing.md) before enabling unsanitized player input. |
| Boss bars | Titles are parsed when the bar is created or updated. |
| Dialogs | See [Dialogs](dialogs.md) for the exact fields Runway checks. |
| Entity text | Covers Adventure component metadata such as text displays and optional nameplates. |
| Items | See [Items and Inventories](items-and-inventories.md) for the difference between inventory items and item update packets. |
