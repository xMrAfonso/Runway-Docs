# How Runway Parses Text

Runway receives text from packets before the player sees it.

<table>
  <thead>
    <tr>
      <th>Mode</th>
      <th>What Runway Parses</th>
      <th>How To Skip One Message</th>
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

If a prefix is required, Runway only parses text that starts with your configured prefix. With the default prefix, this means the text must start with `$`.

```text
$<red>Alert</red>
```

Runway removes the prefix, then parses:

```text
<red>Alert</red>
```

If prefix mode is disabled, Runway tries to parse text automatically. You can opt out of one line by starting it with `!` followed by the prefix.

```text
!$<red>This line will not be parsed</red>
```

## Invalid MiniMessage

If a line contains invalid MiniMessage, Runway leaves that packet unchanged. Use `/runway parse <text>` to test formatting before putting it into another plugin's config.

{% hint style="danger" %}
Invalid tags are not partially fixed. Test complicated gradients, hover text, and click events before shipping them to a live config.
{% endhint %}

## Item Italics

Minecraft displays many item names and lore lines in italics by default. Runway can automatically add `<!italic>` before parsed item text when `disableItalics` is enabled.
