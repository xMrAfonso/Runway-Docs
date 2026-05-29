# Runway Tags

Runway adds a small set of tags for text transforms and action bars.

- `<uppercase>` or `<upper>` converts content to uppercase.
- `<lowercase>` or `<lower>` converts content to lowercase.
- `<smallcaps>` or `<sc>` converts supported letters to small-cap characters.
- `<plain>` keeps visible text and removes nested styling.
- `<actionbar>` or `<ac>` sends content to the player's action bar.

## Text Transform Tags

- Uppercase: `$<uppercase>hello</uppercase>` outputs `HELLO`.
- Lowercase: `$<lowercase>HELLO</lowercase>` outputs `hello`.
- Small caps: `$<smallcaps>RunwayMC</smallcaps>` outputs small-cap characters where supported.
- Plain text: `$<plain><red>Hello</red> <bold>World</bold></plain>` outputs `Hello World`.

The shorter aliases work too: `<upper>`, `<lower>`, and `<sc>`.

## Action Bar

`<actionbar>` sends the enclosed content to the player's action bar and removes it from the original message.

Example:

```text
$<actionbar><green>Quest updated!</green></actionbar>
```

This tag only works with player context.

{% hint style="warning" %}
`<actionbar>` needs a player target. It will not be useful in contexts where Runway cannot identify the receiving player.
{% endhint %}

PlaceholderAPI syntax lives in [PlaceholderAPI](../placeholders/placeholderapi.md).
