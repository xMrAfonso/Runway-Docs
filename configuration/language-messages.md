# Language Messages

Command messages are stored in:

<div style="padding: 14px 16px; border: 1px solid #e2e8f0; border-radius: 10px; background: #fbfdff; margin: 12px 0;">
  <code>plugins/Runway/lang.yml</code>
</div>

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

<div style="padding: 14px 16px; border: 1px solid #d9e7ff; border-radius: 10px; background: #f7fbff; margin-top: 16px;">
  <strong>Tip:</strong> keep command messages short. They are feedback, not announcements.
</div>
