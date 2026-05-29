# Commands and Permissions

| Command | Permission | Purpose |
| --- | --- | --- |
| `/runway reload` | `runway.reload` | Reloads configuration, messages, placeholders, and resolvers. |
| `/runway parse <text>` | `runway.parse` | Parses text and sends a preview to the command sender. |

## `/runway parse <text>`

Example:

```text
/runway parse <gradient:#0050ff:#00d4ff>Hello</gradient>
```

The command adds your configured Runway prefix before parsing, so you do not need to include `$`. It rejects legacy section-sign color codes.

{% hint style="warning" %}
Use MiniMessage tags instead of legacy section-sign color codes.
{% endhint %}
