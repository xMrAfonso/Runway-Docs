# Supported Text Locations

Use this as a map from visible text to the listener that controls it.

- Chat: `listeners.chat`
- System messages: `listeners.systemMessages`
- Action bars: `listeners.actionbar`
- Boss bars: `listeners.bossbar`
- Tab list: `listeners.tablist`
- Titles: `listeners.titles`
- Dialogs: `listeners.dialogs`
- Entity text: `listeners.entityText`
- Player names: `listeners.playerNames`
- Inventory titles: `listeners.inventory.title`
- Inventory items: `listeners.inventory.items`
- Item updates: `listeners.items`

{% hint style="info" %}
If a text location is not changing, check its listener and prefix behavior first.
{% endhint %}

## Notes By Area

- Chat: see [Chat Formatting and Sanitizing](../formatting/chat-formatting-and-sanitizing.md) before enabling unsanitized player input.
- Boss bars: titles are parsed when the bar is created or updated.
- Dialogs: see [Dialogs](dialogs.md) for the exact fields Runway checks.
- Entity text: covers Adventure component metadata such as text displays and optional nameplates.
- Items: see [Items and Inventories](items-and-inventories.md) for the difference between inventory items and item update packets.
