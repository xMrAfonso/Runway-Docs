# Troubleshooting

## My Text Shows The Raw Tags

Check:

- The listener for that text location is enabled.
- The text starts with the configured prefix if a prefix is required.
- The text is sent through a supported packet location.
- The MiniMessage syntax is valid.

Test the same text with:

```text
/runway parse <text>
```

## PlaceholderAPI Placeholders Do Not Work

Check:

- PlaceholderAPI is installed.
- The expansion for that placeholder is installed.
- You are using `<papi:player_name>`, not `%player_name%`, inside MiniMessage text.
- The placeholder has player context if it needs a player.

## MiniPlaceholders Do Not Work

Check:

- MiniPlaceholders is installed and enabled.
- The MiniPlaceholders expansion providing the tag is installed.
- Your `miniPlaceholders.refresh-rate` is not so high that you are seeing stale global values.

## Items Are Italic

Set:

```yaml
disableItalics: true
```

Then reload Runway.

## YAML Fails To Load

Quote formatted values:

```yaml
value: "<gradient:#0050ff:#00d4ff>Hello</gradient>"
```

Common YAML problems:

- Unquoted `#` starts a comment.
- Unquoted `:` can break mappings.
- Incorrect indentation breaks nested sections.
- Tabs are not valid indentation in YAML.

## A Message Disappears

The MiniMessage syntax may be invalid, or a conditional placeholder may be returning empty text.

Check the server console for YAML load warnings and test the message with `/runway parse`.

## Players Can Use Tags In Chat

Keep chat sanitizing enabled:

```yaml
listeners:
  chat:
    sanitize: true
```

Only disable this for trusted environments.

