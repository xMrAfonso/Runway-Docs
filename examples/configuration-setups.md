# Configuration Setups

Copy only the pieces you need into `plugins/Runway/settings.yml`.

## Explicit Formatting Only

Best when you want other plugin configs to stay plain unless you opt in.

```yaml
prefix:
  required: true
  value: $
```

Use:

```text
$<green>This is formatted.
```

## Automatic Formatting

Best when most supported text should accept MiniMessage.

```yaml
prefix:
  required: false
  value: $
```

Use `!$` when one line should stay untouched.

## Safer Public Chat

Keep chat enabled but prevent player-written messages from freely resolving every tag.

```yaml
listeners:
  chat:
    enable: true
    sanitize: true
```

## Menus and Items

Use this when a menu plugin controls inventory titles, item names, or lore.

- Menu titles: `listeners.inventory.title.enable: true`
- Items inside menus: `listeners.inventory.items.enable: true`
- Item update packets: `listeners.items.enable: true`
- Remove default item italics: `disableItalics: true`

## Require Prefix Only For Items

Useful when automatic parsing is fine for messages, but item lore contains lots of literal `<` and `>`.

```yaml
prefix:
  required: false

listeners:
  items:
    require-prefix: true
```

## Debugging A Setup

- Raw tags show: check the listener and prefix mode.
- `/runway parse` works but plugin text does not: the packet location may not be enabled or supported.
- Items are italic: set `disableItalics: true`.
