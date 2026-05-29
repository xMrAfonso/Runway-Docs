# Runway Tags

Runway adds a few tags on top of normal MiniMessage.

## Uppercase

```text
$<uppercase>hello</uppercase>
$<upper>hello</upper>
```

Output:

```text
HELLO
```

## Lowercase

```text
$<lowercase>HELLO</lowercase>
$<lower>HELLO</lower>
```

Output:

```text
hello
```

## Small Caps

```text
$<smallcaps>RunwayMC</smallcaps>
$<sc>RunwayMC</sc>
```

This converts supported letters to small-cap characters.

## Plain

`<plain>` keeps visible text and strips nested MiniMessage styling.

```text
$<plain><red>Hello</red> <bold>World</bold></plain>
```

Output:

```text
Hello World
```

## Action Bar

`<actionbar>` sends the enclosed content to the player's action bar and removes it from the original message.

Aliases:

- `<actionbar>`
- `<ac>`

Example:

```text
$<actionbar><green>Quest updated!</green></actionbar>
```

This tag only works with player context.

## PlaceholderAPI Tag

When PlaceholderAPI is installed and enabled, Runway registers:

```text
<papi:placeholder_name>
<placeholderapi:placeholder_name>
```

Example:

```text
$<green>Hello <papi:player_name>
```

Runway sends `%player_name%` to PlaceholderAPI, then parses the result as MiniMessage.

