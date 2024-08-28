# Equipped Trinket

This condition checks if the entity has a trinket equipped in the specified slot.

Type ID: `shappoli:equipped_trinket`

!!! note
    This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! tip
    Add an `inverted` `apoli:empty` item condition to check if the slot is not empty.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`slot` | [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slot to check for trinket. If not specified, the condition will check for any slot.
`slots` | [Array](../../data_types/array/) of [Trinket Slot](../../data/trinket_slot.md) | *optional* | Slots to check for trinket. If not specified, the condition will check for any slot.
`item_condition` | [Item Condition Type](../../condition/item.md) | | Condition that must be met for the action to trigger.

## Examples

```json
"entity_condition": {
  "type": "shappoli:equipped_trinket",
  "slot": {
    "group": "chest"
  },
  "item_condition": {
    "type": "apoli:empty",
    "inverted": true
  }
}
```

This example checks if the entity has a trinket equipped in any slot of the `chest` group.

```json
"entity_condition": {
  "type": "shappoli:equipped_trinket",
  "slots": [
    {
      "group": "chest"
    },
    {
      "name": "ring"
    }
  ],
  "item_condition": {
    "type": "apoli:ingredient",
    "ingredient": {
      "item": "minecraft:cobblestone"
    }
  }
}
```

This example checks if the entity has a trinket equipped in any slot of the `chest` group or the `ring` slot, and if the equipped trinket is a cobblestone.
