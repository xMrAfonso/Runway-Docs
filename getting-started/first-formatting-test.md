# First Formatting Test

## Use The Parse Command

Run this command in game:

```text
/runway parse <green>Hello from Runway!
```

You should receive a formatted preview message.

## Test Through Another Plugin

Put this in a message from another plugin:

```text
$<gradient:#0050ff:#00d4ff>Hello <bold>player</bold>!</gradient>
```

If your prefix is still `$`, Runway will parse the message and remove the `$`.

## Test Without A Prefix

In `settings.yml`, set:

```yaml
prefix:
  required: false
  value: $
```

Then reload:

```text
/runway reload
```

Now normal MiniMessage text can be parsed without `$`.

To stop one message from being parsed while global prefix mode is disabled, start it with `!$`:

```text
!$<red>This stays unparsed.
```

