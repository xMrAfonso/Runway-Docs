# Custom Placeholder Files

Custom placeholders live in:

```text
plugins/Runway/placeholders/
```

Each `.yml` file is one placeholder group.

{% hint style="success" %}
Split placeholders by purpose: `global.yml`, `ranks.yml`, `events.yml`, and so on.
{% endhint %}

## Text Placeholders

Use `text-placeholders` for simple reusable text.

```yaml
prefix: server

text-placeholders:
  name: "RunwayMC"
  store: "<gradient:#0050ff:#00d4ff>store.example.com</gradient>"
```

With the `server` prefix, use them as:

```text
$Welcome to <server_name>
$Visit <server_store>
```

## Group Prefix

`prefix` is optional. It is useful when a file owns a group of related tags.

- No file prefix with `server_name` creates `<server_name>`.
- `prefix: server` with `name` creates `<server_name>`.
- `prefix: rank` with `vip_badge` creates `<rank_vip_badge>`.

## Group Condition

`condition` can disable every placeholder in the file unless the expression is true.

```yaml
condition: "<event_active> == true"
```

If the condition is false, placeholders from that file return empty text.

For PlaceholderAPI-backed conditions, see [PlaceholderAPI](placeholderapi.md).

## Reloading

After editing placeholder files, run:

```text
/runway reload
```
