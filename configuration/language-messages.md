# Language Messages

Command messages are stored in:

```text
plugins/Runway/lang.yml
```

These messages support MiniMessage, so you can match them to your server style.

| Key | Used when |
| --- | --- |
| `reloadSuccess` | `/runway reload` completes |
| `parseSuccess` | `/runway parse` succeeds |
| `parseFail` | `/runway parse` cannot parse the input |
| `invalidArgument` | A command argument is invalid |
| `unknownCommand` | A subcommand is unknown |
| `noPermission` | A sender lacks permission |
| `notEnoughArguments` | A command is missing required input |

`parseSuccess` can use `<text>`, which is replaced with the parsed preview text.
