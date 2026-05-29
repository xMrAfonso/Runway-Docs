# Commands And Permissions

## `/runway reload`

Reloads Runway configuration, language messages, custom placeholder files, and placeholder resolvers.

Permission:

```text
runway.reload
```

## `/runway parse <text>`

Parses the given text with Runway and sends a preview back to the command sender.

Permission:

```text
runway.parse
```

Example:

```text
/runway parse <gradient:#0050ff:#00d4ff>Hello</gradient>
```

The command automatically adds your configured Runway prefix before parsing, so you do not need to include `$` in the command.

The command rejects text containing the legacy Minecraft section-sign color symbol.
