# Runway Tags

Runway adds a small set of tags for text transforms, action bars, and PlaceholderAPI.

| Tag | Aliases | Purpose |
| --- | --- | --- |
| `<uppercase>` | `<upper>` | Converts content to uppercase. |
| `<lowercase>` | `<lower>` | Converts content to lowercase. |
| `<smallcaps>` | `<sc>` | Converts supported letters to small-cap characters. |
| `<plain>` | None | Keeps visible text and removes nested styling. |
| `<actionbar>` | `<ac>` | Sends content to the player's action bar. |
| `<papi:...>` | `<placeholderapi:...>` | Resolves PlaceholderAPI placeholders. |

## Text Transform Tags

| Goal | Example | Output |
| --- | --- | --- |
| Uppercase | `$<uppercase>hello</uppercase>` | `HELLO` |
| Lowercase | `$<lowercase>HELLO</lowercase>` | `hello` |
| Small caps | `$<smallcaps>RunwayMC</smallcaps>` | Small-cap characters where supported |
| Plain text | `$<plain><red>Hello</red> <bold>World</bold></plain>` | `Hello World` |

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

## PlaceholderAPI Tag

When PlaceholderAPI is installed, use PlaceholderAPI placeholders without percent signs:

```text
<papi:placeholder_name>
<placeholderapi:placeholder_name>
```

```text
$<green>Hello <papi:player_name>
```

Runway sends `%player_name%` to PlaceholderAPI, then parses the result as MiniMessage.
