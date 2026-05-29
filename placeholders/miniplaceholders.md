# MiniPlaceholders

Runway resolves MiniPlaceholders tags during normal MiniMessage parsing when MiniPlaceholders is installed.

{% hint style="info" %}
Use the tag names documented by your MiniPlaceholders expansions.
{% endhint %}

Example:

```text
$<green>Welcome, <player_name>!
```

## Refresh Rate

- Positive values cache global placeholders and refresh every N seconds.
- `0` or lower refreshes on every parse. This is more current, but more expensive.
