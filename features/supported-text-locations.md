# Supported Text Locations

Runway parses text in the packet locations controlled by `settings.yml`.

| Location | Listener |
| --- | --- |
| Chat | `listeners.chat` |
| System messages | `listeners.systemMessages` |
| Action bars | `listeners.actionbar` |
| Boss bars | `listeners.bossbar` |
| Tab list | `listeners.tablist` |
| Titles | `listeners.titles` |
| Dialogs | `listeners.dialogs` |
| Entity text | `listeners.entityText` |
| Player names | `listeners.playerNames` |
| Inventory titles | `listeners.inventory.title` |
| Inventory items | `listeners.inventory.items` |
| Item updates | `listeners.items` |

{% hint style="info" %}
If a text location is not changing, check both the listener and whether the text needs the configured prefix.
{% endhint %}

## Chat

Player chat messages can be parsed. See [Chat Formatting And Sanitizing](../formatting/chat-formatting-and-sanitizing.md).

## System Messages

Messages sent by plugins through system chat can be parsed.

## Action Bars

Action bar packet text can be parsed.

## Boss Bars

Boss bar titles can be parsed when the boss bar is created or its title is updated.

## Tab List

The tab list header and footer can be parsed.

## Titles

Title and subtitle text can be parsed.

## Dialogs

Dialog titles, body text, buttons, inputs, and dialog item descriptions can be parsed.

## Entity Text

Adventure component metadata can be parsed, including text displays and optional nameplate components.

## Player Names

Runway can parse player display names sent through scoreboard team packets and player info packets.

## Items And Inventories

Inventory titles, inventory item names/lore, and item packets can be parsed.
