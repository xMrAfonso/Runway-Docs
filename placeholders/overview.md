# Placeholder Overview

Runway supports three placeholder sources:

- Custom Runway placeholders in `plugins/Runway/placeholders/*.yml`.
- PlaceholderAPI through `<papi:...>` tags and `%runway_...%` expansion output.
- MiniPlaceholders global placeholders when MiniPlaceholders is installed.

Custom Runway placeholders are MiniMessage tags. If you define a placeholder named `server_name`, you use it as:

```text
$Welcome to <server_name>
```

If the placeholder group has a prefix, Runway adds the prefix to the tag name. A group prefix of `global` and a placeholder named `server` becomes:

```text
<global_server>
```

Custom placeholder names are matched in lowercase.

