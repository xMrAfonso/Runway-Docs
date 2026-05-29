# Migration from Older Versions

Runway now separates main settings from placeholder groups.

| Old file | New location |
| --- | --- |
| `plugins/Runway/config.yml` | `plugins/Runway/settings.yml` |
| `plugins/Runway/placeholders.yml` | `plugins/Runway/placeholders/*.yml` |

## Automatic Migration

On startup, Runway checks for older files and migrates them when possible.

| During migration | Result |
| --- | --- |
| `config.yml` is found | Runway creates `settings.yml` when possible. |
| `placeholders.yml` is found | Runway creates `placeholders/migrated.yml` when possible. |
| Old files are preserved | They may be renamed to backups such as `old-config.yml`. |

## Prefix Change

Very old configs used separate `[mm]` and `[p]` prefix behavior. Current Runway uses one prefix:

```yaml
prefix:
  required: true
  value: "[mm]"
```

If you want the old visual marker, set `prefix.value` to `[mm]`.

## Placeholder Folder

Instead of one `placeholders.yml`, put related placeholder groups in separate files:

```text
plugins/Runway/placeholders/global.yml
plugins/Runway/placeholders/ranks.yml
plugins/Runway/placeholders/events.yml
```

Then run:

```text
/runway reload
```

{% hint style="success" %}
Separate files make large placeholder sets easier to review and maintain.
{% endhint %}
