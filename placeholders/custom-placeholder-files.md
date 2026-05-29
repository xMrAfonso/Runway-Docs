# Custom Placeholder Files

Custom placeholders live in:

```text
plugins/Runway/placeholders/
```

Every `.yml` file in that folder is loaded as one placeholder group.

{% hint style="success" %}
Use separate files for separate concerns, such as `global.yml`, `ranks.yml`, and `events.yml`.
{% endhint %}

## Simple Text Placeholders

Use `text-placeholders` for simple reusable text.

```yaml
prefix: server

text-placeholders:
  name: "RunwayMC"
  store: "<gradient:#0050ff:#00d4ff>store.example.com</gradient>"
```

Use them as:

```text
$Welcome to <server_name>
$Visit <server_store>
```

## Group Prefix

`prefix` is optional. Without it, placeholder names are used directly.

| File prefix | Placeholder key | Tag you use |
| --- | --- | --- |
| None | `server_name` | `<server_name>` |
| `server` | `name` | `<server_name>` |
| `rank` | `vip_badge` | `<rank_vip_badge>` |

```yaml
text-placeholders:
  server_name: "RunwayMC"
```

Use:

```text
<server_name>
```

With:

```yaml
prefix: server
text-placeholders:
  name: "RunwayMC"
```

Use:

```text
<server_name>
```

## Group Condition

`condition` can disable every placeholder in the file unless the expression is true.

```yaml
condition: "<papi:player_has_permission_runway.vip> == true"
```

If the condition is false, placeholders from that group insert empty text.

## Reloading

After editing placeholder files, run:

```text
/runway reload
```
