# Language Messages

Command messages are stored in:

```text
plugins/Runway/lang.yml
```

These messages support MiniMessage, so you can match them to your server style.

- `reloadSuccess`: `/runway reload` completes.
- `parseSuccess`: `/runway parse` succeeds.
- `parseFail`: `/runway parse` cannot parse the input.
- `invalidArgument`: a command argument is invalid.
- `unknownCommand`: a subcommand is unknown.
- `noPermission`: a sender lacks permission.
- `notEnoughArguments`: a command is missing required input.

`parseSuccess` can use `<text>`, which is replaced with the parsed preview text.

{% hint style="info" %}
Keep command messages short. They are feedback, not announcements.
{% endhint %}
