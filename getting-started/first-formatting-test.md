# First Formatting Test

Start here when you want to know whether Runway is parsing at all.

<div style="padding: 14px 16px; border: 1px solid #bfe4ce; border-radius: 10px; background: #f7fff9; margin: 14px 0;">
  <strong>Goal:</strong> prove that Runway can parse MiniMessage before you spend time editing a larger plugin config.
</div>

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

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 12px; margin-top: 12px;">
  <a href="how-runway-parses-text.md" style="display: block; padding: 14px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Prefix behavior</strong><br><span style="color: #526070;">When text is parsed or skipped</span></a>
  <a href="../configuration/listeners.md" style="display: block; padding: 14px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Listeners</strong><br><span style="color: #526070;">Choose the text locations Runway edits</span></a>
  <a href="../placeholders/custom-placeholder-files.md" style="display: block; padding: 14px; border: 1px solid #d9e7ff; border-radius: 10px; text-decoration: none; background: #fbfdff;"><strong>Custom tags</strong><br><span style="color: #526070;">Build reusable server text</span></a>
</div>
