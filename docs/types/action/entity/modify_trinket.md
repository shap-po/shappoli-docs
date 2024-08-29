# Modify Trinket

This action modifies trinkets in equipment slots.

Type ID: `shappoli:modify_trinket`
<br>
Alias: `shappoli:modify_trinkets`

!!! note
    This action requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! note
    This action is extremely similar to the [Modify Inventory](https://origins.readthedocs.io/en/latest/types/entity_action_types/modify_inventory/) action, but is specifically for trinkets.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`entity_action` | [Entity Action Type](../../action/entity.md) | *optional* | Action to perform on the entity.
`item_action` | [Item Action Type](../../action/item.md) | *optional* | Action to perform on the trinket.
`item_condition` | [Item Condition Type](../../condition/item.md) | *optional* | Condition that must be met for the action to trigger. If not specified, the action will always trigger.
`slot` | [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slot to modify trinket. If not specified, the action will modify all slots.
`slots` | [Array](../../data_types/array/) of [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slots to modify trinket. If not specified, the action will modify all slots.
`process_mode` | [Process Mode](https://origins.readthedocs.io/en/latest/types/data_types/process_mode/) | "stacks" | Determines how the affected item stacks in the specified inventory are modified.
`limit` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | 0 | Determines the max amount of times the action should modify item stacks in the inventory. If the specified value is <= `0`, then there will be no limit.

## Examples

```json
"entity_action": {
  "type": "shappoli:modify_trinket",
  "item_action": {
    "type": "apoli:consume"
  },
  "slot": {
    "group": "chest"
  }
}
```

This example will consume all trinkets in the slots of the `chest` group.
