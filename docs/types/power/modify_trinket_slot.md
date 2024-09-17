# Modify Trinket Slot

Applies one or more modifiers to trinket slots, that modify their count.

Type ID: `shappoli:modify_trinket_slot`

!!! note
    This power requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! warning
    This power type does not support a `condition`. If the `condition` field is present, it will be ignored. If you wish to check for an entity condition before applying the modifier(s), you can use the [Conditioned Modify Trinket Slot](./conditioned_modify_trinket_slot.md) power type instead.

!!! info
    It is generally better to remove trinket slots than to add them, as added slots will drop players' items upon rejoining the world.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`modifier` | [Slot Entity Attribute Modifier](../data/slot_entity_attribute_modifier.md) | *optional* | Modifier to apply to the trinket slot count.
`modifiers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Slot Entity Attribute Modifier](../data/slot_entity_attribute_modifier.md) | *optional* | Modifiers to apply to the trinket slot count.

## Examples

```json
{
  "type": "shappoli:modify_trinket_slot",
  "modifier": {
    "slot": "chest/necklace",
    "operation": "addition",
    "value": -1
  }
}
```

This example will remove one trinket slot from the `chest/necklace` slot group.
