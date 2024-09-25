# Prevent Trinket Equip/Unequip

Prevents the player from equipping or unequipping a trinket.

Type IDs: `shappoli:prevent_trinket_equip` and `shappoli:prevent_trinket_unequip`

!!! note
    This power requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`slot` | [Trinket Slot](../data/trinket_slot.md) | *optional* | The slot to prevent the player from equipping or unequipping a trinket from.
`slots` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Trinket Slot](../data/trinket_slot.md) | *optional* | The slots to prevent the player from equipping or unequipping a trinket from.
`item_condition` | [Item Condition Type](../condition/item.md) | *optional* | Condition that must be met for the action to trigger.
`allow_in_creative` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `true` | Whether this power is ignored in creative mode.

## Examples

```json
{
  "type": "shappoli:prevent_trinket_equip",
  "slot": {
    "group": "chest"
  }
}
```

This example will prevent the player from equipping any trinket in the `chest` group.

```json
{
  "type": "shappoli:prevent_trinket_unequip",
  "slots": [
    {
      "name": "ring"
    }
  ],
  "allow_in_creative": false
}
```

This example will prevent the player from unequipping any trinket from the `ring` slot, even in creative mode.
