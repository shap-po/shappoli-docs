# Slot Entity Attribute Modifier

A modifier that can change the amount of trinket slots an entity has.

!!! note
    This data type is useless without [Trinkets](https://modrinth.com/mod/trinkets/) installed.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`slot` | [String](https://origins.readthedocs.io/en/latest/types/data_types/string/) | | ID of the trinket slot which will be modified by this modifier.
`operation` | [Attributed Attribute Modifier Operation](https://origins.readthedocs.io/en/latest/types/data_types/attributed_attribute_modifier_operation/) | | The operation which will be performed by this modifier.
`value` | [Float](https://origins.readthedocs.io/en/latest/types/data_types/float/) | | The value to use for the modifier operation.
`name` | [String](https://origins.readthedocs.io/en/latest/types/data_types/string/) | *optional* | A descriptive name for the modifier, describing where it comes from.

## Examples

```json
"modifier": {
  "slot": "chest/necklace",
  "operation": "addition",
  "value": 2
}
```

This example will add `2` trinket slots of the `necklace` type to the `chest` group.
