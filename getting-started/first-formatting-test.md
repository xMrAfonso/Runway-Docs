# First Formatting Test

Start here when you want to know whether Runway is parsing at all.

## Use The Parse Command

Run this command in game:

```text
/runway parse <green>Hello from Runway!
```

You should get a formatted preview back.

{% hint style="success" %}
If this command works but another plugin's text does not, the issue is probably a listener, prefix, or packet location.
{% endhint %}

## Test Through Another Plugin

Put this in a message from another plugin:

```text
$<gradient:#0050ff:#00d4ff>Hello <bold>player</bold>!</gradient>
```

If your prefix is still `$`, Runway removes it and formats the rest.

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

Now MiniMessage can be parsed without `$`.

To leave one message untouched, start it with `!$`:

```text
!$<red>This stays unparsed.
```

## What to Try Next

| Goal | Next page |
| --- | --- |
| Understand prefix behavior | [How Runway Parses Text](how-runway-parses-text.md) |
| Enable or disable text locations | [Listeners](../configuration/listeners.md) |
| Build reusable tags | [Custom Placeholder Files](../placeholders/custom-placeholder-files.md) |
