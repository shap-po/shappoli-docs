# Equipped Trinket Count

Checks if this item or items of the same type are equipped in a trinket slot.

Type ID: `shappoli:equipped_trinket_count`

!!! note
    This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`slot` | [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slot to check. If not specified, the condition will check for any slot.
`slots` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slots to check. If not specified, the condition will check for any slot.
`comparison` | [Comparison](https://origins.readthedocs.io/en/latest/types/data_types/comparison/) | `>=` | The comparison to use when comparing the amount of equipped trinkets.
`compare_to` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | `1` | The amount of equipped trinkets to compare with.

## Examples

```json
"condition": {
  "type": "shappoli:equipped_trinket_count",
  "slot": {
    "group": "chest"
  }
}
```

This example checks if the entity has at least 1 trinket of the same type equipped in any slot of the `chest` group.
