# Migration From Older Versions

Older Runway versions used:

```text
plugins/Runway/config.yml
plugins/Runway/placeholders.yml
```

Current versions use:

```text
plugins/Runway/settings.yml
plugins/Runway/placeholders/*.yml
```

## Automatic Migration

On startup, Runway checks for older files and migrates them when possible.

Typical results:

- `config.yml` becomes `settings.yml`.
- `placeholders.yml` becomes `placeholders/migrated.yml`.
- Old files are renamed to backup files such as `old-config.yml` and `old-placeholders.yml`.

## Prefix Change

Very old configs used separate `[mm]` and `[p]` prefix behavior. Current Runway uses one configured prefix:

```yaml
prefix:
  required: true
  value: "[mm]"
```

If you want the old visual marker, set `prefix.value` to `[mm]`.

## Placeholder Folder

Instead of one `placeholders.yml`, put each placeholder group in its own file:

```text
plugins/Runway/placeholders/global.yml
plugins/Runway/placeholders/ranks.yml
plugins/Runway/placeholders/events.yml
```

Then run:

```text
/runway reload
```

