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
`tick_rate` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | `20` | The frequency (in ticks) with which to check the condition. Lower values mean the condition changes are detected more quickly, but this comes at a potentially huge performance cost.
`apply_on_added` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `true` | Whether to try to apply the modifier when a power is added. If `false`, the first application will be delayed for `tick_rate` ticks. This is useful for global powers, that are dependent on player's origins, as they are added before the origins are set.

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

### Global Power Example

`data/trinkets/slots/my_group/my_slot.json`
```json
{
    "icon": "trinkets:gui/slots/ring",
    "order": 0,
    "amount": 1,
    "validator_predicates": ["trinkets:tag"],
    "drop_rule": "keep"
}
```
`data/trinkets/entities/my_mod.json`
```json
{
  "entities": [
    "player"
  ],
  "slots": [
    "my_group/my_slot"
  ]
}
```
`data/my_mod/powers/restrict_slots.json`
```json
{
  "type": "shappoli:conditioned_modify_trinket_slot",
  "modifier": {
    "slot": "my_group/my_slot",
    "operation": "addition",
    "value": -1
  },
  "condition": {
    "type": "origins:origin",
    "origin": "my_mod:my_origin",
    "inverted": true
  },
  "apply_on_added": false
}
```
`data/my_mod/global_powers/slot_restriction.json`
```json
{
  "entity_types": [
    "minecraft:player"
  ],
  "powers": [
    "my_mod:restrict_slots"
  ]
}
```

This example will add slot `my_group/my_slot`, that is only available to entities with the origin `my_mod:my_origin`.
