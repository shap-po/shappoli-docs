# Action On Trinket Change

This power is triggered when a trinket is equipped or unequipped. 

Type ID: `shappoli:action_on_trinket_change`

!!! note
    This power requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! note
    When slot is emptied, the equip action will be triggered with `minecraft:air` item.
    The same goes for the unequip action.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`entity_action_on_equip` | [Entity Action Type](../action/entity.md) | *optional* | Action to perform when the trinket is equipped.
`entity_action_on_unequip` | [Entity Action Type](../action/entity.md) | *optional* | Action to perform when the trinket is unequipped.
`item_action_on_equip` | [Item Action Type](../action/item.md) | *optional* | Action to perform when the trinket is equipped.
`item_action_on_unequip` | [Item Action Type](../action/item.md) | *optional* | Action to perform when the trinket is unequipped.
`item_condition` | [Item Condition Type](../condition/item.md) | | Condition that must be met for the action to trigger.
`slot` | [Trinket Slot](../data/trinket_slot.md) | *optional* | Slot to check for trinket. If not specified, the action will trigger for any slot.
`slots` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Trinket Slot](../data/trinket_slot.md) | *optional* | Slots to check for trinket. If not specified, the action will trigger for any slot.

## Examples

```json
{
  "type": "shappoli:action_on_trinket_change",
  "entity_action_on_equip": {
    "type": "apoli:execute_command",
    "command": "say Equipped a trinket!"
  },
  "entity_action_on_unequip": {
    "type": "apoli:execute_command",
    "command": "say Unequipped a trinket!"
  },
  "item_condition": {
    "type": "apoli:empty",
    "inverted": true
  }
}
```

This example will send a message when a player with this power equips or unequips a trinket.

```json
{
  "type": "shappoli:action_on_trinket_change",
  "item_action_on_equip": {
    "type": "apoli:consume"
  },
  "slot": {
    "group": "chest"
  },
  "item_condition": {
    "type": "apoli:empty",
    "inverted": true
  }
}
```

This example will consume any trinket as soon as it is equipped in any slot of the `chest` group.
