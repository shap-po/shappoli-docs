# Has Trinket Slot

Compares the amount of trinket slots an entity has to a specified value.

Type ID: `shappoli:trinket_slot_count`

!!! note
This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

## Fields

| Field        | Type                                                                                                                     | Default    | Description                                                              |
| ------------ | ------------------------------------------------------------------------------------------------------------------------ | ---------- | ------------------------------------------------------------------------ |
| `slot`       | [Trinket Slot](../../data/trinket_slot.md)                                                                               | _optional_ | Slot to check. If not specified, the condition will check for any slot.  |
| `slots`      | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array//) of [Trinket Slot](../../data/trinket_slot.md) | _optional_ | Slots to check. If not specified, the condition will check for any slot. |
| `comparison` | [Comparison](https://origins.readthedocs.io/en/latest/types/data_types/comparison/)                                      | `>=`       | The comparison to use when comparing the amount of slots.                |
| `compare_to` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/)                                            | `1`        | The amount of slots to compare with.                                     |

## Examples

```json
"condition": {
  "type": "shappoli:trinket_slot_count",
  "slot": {
    "group": "chest"
  }
}
```

This example checks if the entity has at least 1 trinket slot in the `chest` group.
