# How Runway Parses Text

Runway receives text from packets before the player sees it.

If a prefix is required, Runway only parses text that starts with your configured prefix. With the default prefix, this means the text must start with `$`.

```text
$<red>Alert</red>
```

Runway removes the prefix, then parses:

```text
<red>Alert</red>
```

If prefix mode is disabled, Runway tries to parse text automatically. You can opt out of one line by starting it with `!` followed by the prefix.

```text
!$<red>This line will not be parsed</red>
```

## Invalid MiniMessage

If a line contains invalid MiniMessage, Runway leaves that packet unchanged. Use `/runway parse <text>` to test formatting before putting it into another plugin's config.

## Item Italics

Minecraft displays many item names and lore lines in italics by default. Runway can automatically add `<!italic>` before parsed item text when `disableItalics` is enabled.

