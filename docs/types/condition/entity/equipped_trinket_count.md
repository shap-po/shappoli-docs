# Equipped Trinket

This condition checks if the entity has a trinket equipped in the specified slot.

Type ID: `shappoli:equipped_trinket_count`

!!! note
This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! tip
Add an `inverted` `apoli:empty` item condition to check if the slot is not empty.

## Fields

| Field            | Type                                                                                                                     | Default    | Description                                                                          |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------ | ---------- | ------------------------------------------------------------------------------------ |
| `slot`           | [Trinket Slot](../../data/trinket_slot.md)                                                                               | _optional_ | Slot to check for trinket. If not specified, the condition will check for any slot.  |
| `slots`          | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array//) of [Trinket Slot](../../data/trinket_slot.md) | _optional_ | Slots to check for trinket. If not specified, the condition will check for any slot. |
| `item_condition` | [Item Condition Type](../../condition/item.md)                                                                           |            | Condition that must be met by the equipped trinket.                                  |
| `comparison`     | [Comparison](https://origins.readthedocs.io/en/latest/types/data_types/comparison/)                                      | `>=`       | The comparison to use when comparing the amount of equipped trinkets.                |
| `compare_to`     | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/)                                            | `1`        | The amount of equipped trinkets to compare with.                                     |

## Examples

```json
"entity_condition": {
  "type": "shappoli:equipped_trinket_count",
  "slot": {
    "group": "chest"
  },
  "comparison": ">",
  "compare_to": 1,
  "item_condition": {
    "type": "apoli:empty",
    "inverted": true
  }
}
```

This example checks if the entity has at least 2 trinkets equipped in any slot of the `chest` group.

```json
"entity_condition": {
  "type": "shappoli:equipped_trinket_count",
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
