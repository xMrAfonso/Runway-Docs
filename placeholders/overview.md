# Placeholder Overview

Runway supports three placeholder sources:

| Source | Where it comes from | How you use it |
| --- | --- | --- |
| Custom Runway placeholders | `plugins/Runway/placeholders/*.yml` | `<server_name>` |
| PlaceholderAPI | PlaceholderAPI plugin and expansions | `<papi:player_name>` |
| MiniPlaceholders | MiniPlaceholders plugin and expansions | Expansion-specific MiniPlaceholders tags |

{% hint style="info" %}
Custom Runway placeholders are MiniMessage tags, so they use angle brackets rather than percent signs.
{% endhint %}

Custom Runway placeholders are MiniMessage tags. If you define a placeholder named `server_name`, you use it as:

```text
$Welcome to <server_name>
```

If the placeholder group has a prefix, Runway adds the prefix to the tag name. A group prefix of `global` and a placeholder named `server` becomes:

```text
<global_server>
```

Custom placeholder names are matched in lowercase.

## Good Naming Patterns

| Pattern | Example | Why it helps |
| --- | --- | --- |
| Prefix by domain | `<server_name>` | Keeps global server tags grouped. |
| Prefix by feature | `<shop_sale>` | Makes large configs easier to scan. |
| Keep names lowercase | `<rank_badge>` | Matches Runway's lowercase lookup behavior. |
