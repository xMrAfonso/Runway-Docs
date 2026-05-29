# How Runway Parses Text

Runway looks at outgoing text packets before the player sees them. Whether it parses a line mostly comes down to prefix mode and the listener for that packet.

<table style="width: 100%; border-collapse: separate; border-spacing: 0; margin: 16px 0; border: 1px solid #d9e7ff; border-radius: 10px; overflow: hidden;">
  <thead>
    <tr style="background: #f7fbff;">
      <th style="text-align: left; padding: 12px;">Mode</th>
      <th style="text-align: left; padding: 12px;">What Runway parses</th>
      <th style="text-align: left; padding: 12px;">How to skip one message</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;"><code>prefix.required: true</code></td>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;">Only text that starts with the configured prefix.</td>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;">Leave the prefix off.</td>
    </tr>
    <tr>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;"><code>prefix.required: false</code></td>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;">Supported text automatically, unless a listener requires the prefix.</td>
      <td style="padding: 12px; border-top: 1px solid #e7eef8;">Start with <code>!</code> followed by the prefix, such as <code>!$</code>.</td>
    </tr>
  </tbody>
</table>

With `prefix.required: true`, only prefixed text is parsed:

```text
$<red>Alert</red>
```

Runway removes the prefix and parses the rest:

```text
<red>Alert</red>
```

With `prefix.required: false`, supported text is parsed automatically. Add `!` before the prefix to opt out for one line:

```text
!$<red>This line will not be parsed</red>
```

## Invalid MiniMessage

If a line contains invalid MiniMessage, Runway leaves that packet unchanged. Use `/runway parse <text>` to test formatting before putting it into another plugin's config.

{% hint style="danger" %}
Runway does not try to repair broken MiniMessage. Test complicated gradients, hover text, and click events with `/runway parse`.
{% endhint %}

## Item Italics

Minecraft displays many item names and lore lines in italics by default. Runway can automatically add `<!italic>` before parsed item text when `disableItalics` is enabled.
