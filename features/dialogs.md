# Dialogs

Runway can parse Minecraft dialog packets when the `dialogs` listener is enabled.

```yaml
listeners:
  dialogs:
    enable: true
    require-prefix: false
```

## Parsed Dialog Parts

Runway parses:

- Dialog title
- External title
- Plain message body text
- Dialog item names and lore
- Dialog item descriptions
- Text input labels
- Text input initial values
- Boolean input labels
- Single option input labels
- Single option display text
- Number range labels
- Button labels
- Button tooltips

## Plain Text Fields

Some dialog fields are plain strings, not rich components. Runway still parses them, then converts the result back to plain text. Formatting colors cannot remain in those plain string fields, but placeholders and text-transforming tags can still be useful.

