# Commands and Permissions

- `/runway reload` requires `runway.reload` and reloads configuration, messages, placeholders, and resolvers.
- `/runway parse <text>` requires `runway.parse` and sends a parsed preview to the command sender.

## `/runway parse <text>`

Example:

```text
/runway parse <gradient:#0050ff:#00d4ff>Hello</gradient>
```

The command adds your configured Runway prefix before parsing, so you do not need to include `$`. It rejects legacy section-sign color codes.

{% hint style="warning" %}
Use MiniMessage tags instead of legacy section-sign color codes.
{% endhint %}
