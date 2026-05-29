# Troubleshooting

Start with the symptom, then test the exact text with `/runway parse <text>` when possible.

| Symptom | First thing to check |
| --- | --- |
| Raw tags are visible | Listener, prefix, and MiniMessage syntax |
| PlaceholderAPI values are blank | See [PlaceholderAPI](../placeholders/placeholderapi.md) |
| MiniPlaceholders values are stale | `miniPlaceholders.refresh-rate` |
| Items are italic | `disableItalics` |
| YAML fails to load | Quotes, indentation, and tabs |
| Message disappears | Invalid MiniMessage or empty conditional output |
| Players can use tags in chat | `listeners.chat.sanitize` |

## Raw Tags Are Visible

Test the same text first:

```text
/runway parse <red>Example
```

If the command works, check the listener and prefix for the original text location.

## Placeholders Are Blank

| Placeholder type | Check |
| --- | --- |
| PlaceholderAPI | Use the checks in [PlaceholderAPI](../placeholders/placeholderapi.md). |
| MiniPlaceholders | Plugin installed, expansion installed, and refresh rate is not hiding recent changes. |
| Custom Runway | File loaded, tag name matches, and any group condition is true. |

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

| Problem | Fix |
| --- | --- |
| Unquoted `#` | Quote values with hex colors. |
| Unquoted `:` | Quote long formatted strings and URLs. |
| Broken indentation | Use spaces consistently. |
| Tabs | Replace tabs with spaces. |

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
