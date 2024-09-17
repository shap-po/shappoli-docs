# Equippable Trinket

Checks if the item can be equipped in a trinket slot.

Type ID: `shappoli:equippable_trinket`

!!! note
This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

## Fields

| Field        | Type                                                                                                                     | Default    | Description                                                              |
| ------------ | ------------------------------------------------------------------------------------------------------------------------ | ---------- | ------------------------------------------------------------------------ |
| `slot`       | [Trinket Slot](../../data/trinket_slot.md)                                                                               | _optional_ | Slot to check. If not specified, the condition will check for any slot.  |
| `slots`      | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array//) of [Trinket Slot](../../data/trinket_slot.md) | _optional_ | Slots to check. If not specified, the condition will check for any slot. |
| `only_empty` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/)                                            | `false`    | Whether the slot must be empty for the condition to pass.                |

## Examples

```json
"condition": {
  "type": "shappoli:equippable_trinket",
  "slot": {
    "group": "chest"
  }
}
```

This example checks if the item can be equipped in a slot from the `chest` group.
