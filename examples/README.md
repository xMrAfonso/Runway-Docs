# Examples

Use these pages when you want a starting point instead of building a config from scratch.

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 12px; margin: 14px 0;">
  <a href="configuration-setups.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Configuration setups</strong><br><span style="color: #526070;">Prefix modes, listeners, chat, items, and menus.</span></a>
  <a href="message-recipes.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Message recipes</strong><br><span style="color: #526070;">Small MiniMessage patterns for common plugin text.</span></a>
  <a href="placeholder-recipes.md" style="display: block; padding: 16px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Placeholder recipes</strong><br><span style="color: #526070;">Reusable server tags and placeholder file layouts.</span></a>
</div>

{% hint style="info" %}
For PlaceholderAPI-specific syntax and examples, use [PlaceholderAPI](../placeholders/placeholderapi.md).
{% endhint %}

## Before You Paste

| Check | Why |
| --- | --- |
| Quote formatted YAML values | Hex colors, colons, and URLs can confuse YAML. |
| Match your prefix mode | Examples use `$` unless noted. |
| Enable the right listener | A perfect message will still stay plain if its listener is off. |
| Test with `/runway parse` | It catches MiniMessage syntax problems early. |
