# Language Messages

Command messages are stored in:

```text
plugins/Runway/lang.yml
```

These messages support MiniMessage.

{% hint style="success" %}
Language messages are a good place to use your server colors, gradients, and reusable placeholders.
{% endhint %}

Common keys:

```yaml
reloadSuccess: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Configuration was reloaded successfully!"
parseSuccess: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Parsed text: <gray><text>"
parseFail: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Failed to parse the text. Make sure it can be parsed!"
invalidArgument: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Invalid argument. Please use a valid argument!"
unknownCommand: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Sorry but that command is unknown. Please try again!"
noPermission: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>You do not have permission to use this command!"
notEnoughArguments: "<gradient:#0050ff:#0099ff>Runway</gradient><gray> | <white>Not enough arguments. Please use a valid argument!"
```

`parseSuccess` can use `<text>`, which is replaced with the parsed preview text.

| Key | Used when |
| --- | --- |
| `reloadSuccess` | `/runway reload` completes |
| `parseSuccess` | `/runway parse` succeeds |
| `parseFail` | `/runway parse` cannot parse the input |
| `invalidArgument` | A command argument is invalid |
| `unknownCommand` | A subcommand is unknown |
| `noPermission` | A sender lacks permission |
| `notEnoughArguments` | A command is missing required input |
