# First Formatting Test

This page gives you a fast smoke test before you start editing larger plugin configs.

## Use The Parse Command

Run this command in game:

```text
/runway parse <green>Hello from Runway!
```

You should receive a formatted preview message.

{% hint style="success" %}
The parse command is the fastest way to separate MiniMessage syntax problems from listener or plugin integration problems.
{% endhint %}

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

## What To Try Next

| Goal | Next page |
| --- | --- |
| Understand prefix behavior | [How Runway Parses Text](how-runway-parses-text.md) |
| Enable or disable text locations | [Listeners](../configuration/listeners.md) |
| Build reusable tags | [Custom Placeholder Files](../placeholders/custom-placeholder-files.md) |
