# Chat Formatting and Sanitizing

Player chat has one extra concern: players can type the text themselves. That makes `sanitize` the important setting.

| Setting | Recommended | Why |
| --- | --- | --- |
| `enable` | `true` if you want chat formatting | Lets Runway inspect chat packets. |
| `require-prefix` | Depends on your server | Prefix mode gives players explicit control. |
| `sanitize` | `true` on public servers | Limits what player-written chat can resolve. |

## Sanitized Chat

When `sanitize` is `true`, player-written chat is protected from normal custom placeholders. Players can still be shown through your chat renderer, but they cannot freely trigger every Runway tag from their own messages.

{% hint style="success" %}
Use `sanitize: true` on public servers.
{% endhint %}

## Unsanitized Chat

When `sanitize` is `false`, player chat can use the same tags as the chat renderer. Only do this for trusted or heavily filtered chat.

## Per-Message Prefix

If chat requires a prefix, players must start their message with it:

```text
$<green>Hello
```

If chat parses automatically, `!$` skips Runway for one message when `$` is the configured prefix.
