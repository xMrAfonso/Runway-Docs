# MiniMessage Basics

Runway uses Adventure MiniMessage. You can use normal MiniMessage tags in text that Runway parses.

{% hint style="info" %}
These examples include the default Runway prefix `$`. If your prefix is different, replace `$` with your configured value.
{% endhint %}

## Common Tags

| Goal | Example |
| --- | --- |
| Named color | `$<red>Red text` |
| Hex color | `$<#00d4ff>Hex color` |
| Bold text | `$<bold>Bold</bold>` |
| Remove item italics | `$<!italic>Not italic` |
| Gradient | `$<gradient:#0050ff:#00d4ff>Gradient text</gradient>` |

## Colors

```text
$<red>Red text
$<green>Green text
$<#00d4ff>Hex color
```

## Decoration

```text
$<bold>Bold</bold>
$<italic>Italic</italic>
$<!italic>Not italic
$<underlined>Underlined</underlined>
```

## Gradients

```text
$<gradient:#0050ff:#00d4ff>Gradient text</gradient>
```

## Click And Hover

```text
$<hover:show_text:'<gray>Click to join'><click:run_command:'/server lobby'><green>Lobby</green></click></hover>
```

## Keep YAML Valid

When putting MiniMessage in YAML, quote values that contain `:`, `#`, `<`, `>`, or long formatted strings.

Good:

```yaml
message: "$<gradient:#0050ff:#00d4ff>Hello</gradient>"
```

{% hint style="warning" %}
In YAML, an unquoted `#` starts a comment. Quote hex colors and gradients.
{% endhint %}
