# Placeholder Overview

Runway supports three placeholder sources:

| Source | Where it comes from | How you use it |
| --- | --- | --- |
| Custom Runway placeholders | `plugins/Runway/placeholders/*.yml` | `<server_name>` |
| PlaceholderAPI | PlaceholderAPI plugin and expansions | `<papi:player_name>` |
| MiniPlaceholders | MiniPlaceholders plugin and expansions | Expansion-specific MiniPlaceholders tags |

{% hint style="info" %}
Runway placeholders are MiniMessage tags. Use angle brackets in Runway text.
{% endhint %}

If you define `server_name`, use it like this:

```text
$Welcome to <server_name>
```

Group prefixes are added to the tag name. A group prefix of `global` and a placeholder named `server` becomes:

```text
<global_server>
```

## Good Naming Patterns

| Pattern | Example | Why it helps |
| --- | --- | --- |
| Prefix by domain | `<server_name>` | Keeps global server tags grouped. |
| Prefix by feature | `<shop_sale>` | Makes large configs easier to scan. |
| Keep names lowercase | `<rank_badge>` | Matches Runway's lowercase lookup behavior. |
