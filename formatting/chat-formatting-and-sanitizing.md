# Chat Formatting And Sanitizing

Runway can parse player chat through the `listeners.chat` section.

```yaml
listeners:
  chat:
    enable: true
    require-prefix: false
    sanitize: true
```

## Sanitized Chat

When `sanitize` is `true`, player-written chat content is protected from normal custom placeholders. Players can still have their message rendered through the server's chat renderer, but they cannot freely use every custom Runway tag in their own chat text.

This is the recommended setting for public servers.

## Unsanitized Chat

When `sanitize` is `false`, player chat can use the same tags as the chat renderer.

Only use this if you trust the people who can chat, or if another plugin already controls and filters the message content.

## Per-Message Prefix

If chat requires a prefix, players must start their message with the configured prefix:

```text
$<green>Hello
```

If chat does not require a prefix and global parsing is enabled, players can start a message with `!$` to skip Runway parsing when `$` is the configured prefix.

