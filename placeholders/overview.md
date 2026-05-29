# Placeholder Overview

Runway supports three placeholder sources:

- Custom Runway placeholders from `plugins/Runway/placeholders/*.yml`, used as tags such as `<server_name>`.
- PlaceholderAPI from the PlaceholderAPI plugin and its expansions. See [PlaceholderAPI](placeholderapi.md).
- MiniPlaceholders from the MiniPlaceholders plugin and its expansions.

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

- Prefix by domain, such as `<server_name>`, to keep global server tags grouped.
- Prefix by feature, such as `<shop_sale>`, to make large configs easier to scan.
- Keep names lowercase, such as `<rank_badge>`, to match Runway's lowercase lookup behavior.
