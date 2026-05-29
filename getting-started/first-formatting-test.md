# First Formatting Test

Start here when you want to know whether Runway is parsing at all.

{% hint style="info" %}
Goal: prove that Runway can parse MiniMessage before you spend time editing a larger plugin config.
{% endhint %}

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

| Goal | Page |
| --- | --- |
| Prefix behavior | [How Runway Parses Text](how-runway-parses-text.md) |
| Text locations | [Listeners](../configuration/listeners.md) |
| Reusable tags | [Custom Placeholder Files](../placeholders/custom-placeholder-files.md) |
