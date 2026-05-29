# How Runway Parses Text

Runway looks at outgoing text packets before the player sees them. Whether it parses a line mostly comes down to prefix mode and the listener for that packet.

<table>
  <thead>
    <tr>
      <th>Mode</th>
      <th>What Runway Parses</th>
      <th>How to skip one message</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>prefix.required: true</code></td>
      <td>Only text that starts with the configured prefix.</td>
      <td>Leave the prefix off.</td>
    </tr>
    <tr>
      <td><code>prefix.required: false</code></td>
      <td>Supported text automatically, unless a listener requires the prefix.</td>
      <td>Start with <code>!</code> followed by the prefix, such as <code>!$</code>.</td>
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
