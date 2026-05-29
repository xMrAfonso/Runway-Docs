# MiniMessage Basics

Runway uses Adventure MiniMessage, so most formatting you already know from Adventure works here too.

{% hint style="info" %}
The examples include the default `$` prefix. Replace it if your server uses a different one.
{% endhint %}

## Quick Reference

| Goal | Example |
| --- | --- |
| Named color | `$<red>Red text` |
| Hex color | `$<#00d4ff>Hex color` |
| Bold text | `$<bold>Bold</bold>` |
| Remove item italics | `$<!italic>Not italic` |
| Underline | `$<underlined>Underlined</underlined>` |
| Gradient | `$<gradient:#0050ff:#00d4ff>Gradient text</gradient>` |
| Hover and click | `$<hover:show_text:'<gray>Click to join'><click:run_command:'/server lobby'><green>Lobby</green></click></hover>` |

## Keep YAML Valid

Quote formatted values in YAML, especially when they contain `:`, `#`, `<`, or `>`.

```yaml
message: "$<gradient:#0050ff:#00d4ff>Hello</gradient>"
```

{% hint style="warning" %}
In YAML, an unquoted `#` starts a comment. Quote hex colors and gradients.
{% endhint %}
