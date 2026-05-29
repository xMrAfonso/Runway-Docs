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

| Refresh rate | Behavior |
| --- | --- |
| Positive number | Cache global placeholders and refresh every N seconds. |
| `0` or lower | Refresh on every parse. More current, but more expensive. |
