# Dialogs

Runway can parse Minecraft dialog packets when the `dialogs` listener is enabled.

```yaml
listeners:
  dialogs:
    enable: true
    require-prefix: false
```

{% hint style="info" %}
Dialog support covers both visible components and several plain string fields. Plain string fields can still use placeholders, but they cannot keep color formatting after conversion back to plain text.
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

Some dialog fields are plain strings, not rich components. Runway still parses them, then converts the result back to plain text. Formatting colors cannot remain in those plain string fields, but placeholders and text-transforming tags can still be useful.
