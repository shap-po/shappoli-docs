# Conditioned Modify Trinket Slot

Applies one or more modifiers to trinket slots, that modify their count; may depend on a `condition`.

Type ID: `shappoli:conditioned_modify_trinket_slot`

!!! note
    This power requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! note
    You can use the [Modify Trinket Slot (Power Type)](./modify_trinket_slot.md) if an entity condition is not needed.

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
  "type": "shappoli:conditioned_modify_trinket_slot",
  "modifier": {
    "slot": "chest/necklace",
    "operation": "addition",
    "value": -1
  },
  "condition": {
    "type": "apoli:on_block",
    "block_condition": {
      "type": "apoli:block",
      "block": "minecraft:stone"
    }
  }
}
```

This example will remove one trinket slot from the `chest/necklace` slot group if the entity is standing on a `minecraft:stone` block.
