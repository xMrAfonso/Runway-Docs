# Listeners

Listeners control which outgoing text locations Runway is allowed to edit.

Each listener has:

```yaml
enable: true
require-prefix: false
```

`enable` turns that area on or off.

`require-prefix` forces the global prefix for that listener when `prefix.required` is disabled globally.

If `prefix.required` is enabled globally, every listener requires the prefix regardless of its own `require-prefix` value.

## Example

This parses most text automatically, but still requires `$` for item names and lore:

```yaml
prefix:
  required: false
  value: $

listeners:
  items:
    enable: true
    require-prefix: true
```

## Available Listeners

```yaml
listeners:
  chat:
    enable: true
    require-prefix: false
    sanitize: true
  systemMessages:
    enable: true
    require-prefix: false
  actionbar:
    enable: true
    require-prefix: false
  bossbar:
    enable: true
    require-prefix: false
  tablist:
    enable: true
    require-prefix: false
  titles:
    enable: true
    require-prefix: false
  dialogs:
    enable: true
    require-prefix: false
  entityText:
    enable: true
    require-prefix: false
  playerNames:
    enable: true
    require-prefix: false
  inventory:
    title:
      enable: true
      require-prefix: false
    items:
      enable: true
      require-prefix: false
  items:
    enable: true
    require-prefix: false
```

Some older generated files may have different listener names. Keep the format your installed version generated unless you are migrating with a newer Runway release.

