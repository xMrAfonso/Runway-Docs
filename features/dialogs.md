# Dialogs

Runway can parse Minecraft dialog packets when `listeners.dialogs.enable` is `true`.

{% hint style="info" %}
Dialog support covers rich components and several plain string fields.
{% endhint %}

## Parsed Dialog Parts

| Dialog area | Parsed fields |
| --- | --- |
| Titles and body | Dialog title, external title, plain message body text |
| Items | Dialog item names, lore, and descriptions |
| Inputs | Text input labels, initial values, boolean labels, number range labels |
| Options | Single option labels and display text |
| Buttons | Button labels and tooltips |

## Plain Text Fields

Some dialog fields are plain strings, not rich components. Runway still parses them, then converts the result back to plain text. Colors cannot survive that conversion, but placeholders and text-transforming tags can still be useful.
