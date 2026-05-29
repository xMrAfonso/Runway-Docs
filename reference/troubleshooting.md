# Troubleshooting

Start with the symptom, then test the exact text with `/runway parse <text>` when possible.

- Raw tags are visible: check the listener, prefix, and MiniMessage syntax.
- PlaceholderAPI values are blank: see [PlaceholderAPI](../placeholders/placeholderapi.md).
- MiniPlaceholders values are stale: check `miniPlaceholders.refresh-rate`.
- Items are italic: check `disableItalics`.
- YAML fails to load: check quotes, indentation, and tabs.
- A message disappears: check for invalid MiniMessage or empty conditional output.
- Players can use tags in chat: check `listeners.chat.sanitize`.

## Raw Tags Are Visible

Test the same text first:

```text
/runway parse <red>Example
```

If the command works, check the listener and prefix for the original text location.

## Placeholders Are Blank

- PlaceholderAPI: use the checks in [PlaceholderAPI](../placeholders/placeholderapi.md).
- MiniPlaceholders: confirm the plugin and expansion are installed, and the refresh rate is not hiding recent changes.
- Custom Runway placeholders: confirm the file loaded, the tag name matches, and any group condition is true.

Inside Runway text, PlaceholderAPI uses Runway's tag syntax. The full syntax is on the PlaceholderAPI page.

## Item Text Is Italic

Set:

```yaml
disableItalics: true
```

Then reload Runway.

## YAML Fails To Load

Quote formatted values:

```yaml
value: "<gradient:#0050ff:#00d4ff>Hello</gradient>"
```

- Unquoted `#`: quote values with hex colors.
- Unquoted `:`: quote long formatted strings and URLs.
- Broken indentation: use spaces consistently.
- Tabs: replace tabs with spaces.

{% hint style="warning" %}
YAML accepts spaces for indentation, not tabs. Many config issues that look like Runway issues are actually YAML parse failures.
{% endhint %}

## A Message Disappears

The MiniMessage syntax may be invalid, or a conditional placeholder may be returning empty text.

Check the server console for YAML load warnings, then test the message with `/runway parse`.

## Players Can Use Tags In Chat

Keep chat sanitizing enabled:

```yaml
listeners:
  chat:
    sanitize: true
```

Only disable this for trusted environments.
