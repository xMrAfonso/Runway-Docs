# MiniPlaceholders

Runway supports MiniPlaceholders when the MiniPlaceholders plugin is installed and enabled.

MiniPlaceholders tags are resolved together with Runway's normal MiniMessage parsing.

Example:

```text
$<green>Welcome, <player_name>!
```

Use the placeholder names provided by your MiniPlaceholders expansions.

## Refresh Rate

Runway caches MiniPlaceholders audience global placeholders and refreshes them based on `settings.yml`.

```yaml
miniPlaceholders:
  refresh-rate: 30
```

Lower values update more often. Higher values reduce refresh work. Use `0` or lower only if you need every parse to refresh the global placeholders.

