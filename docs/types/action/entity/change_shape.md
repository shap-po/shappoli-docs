# Change Shape

Changes player's shape into a different entity.

Type ID: `shappoli:change_shape`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! warning
    This action only works on players.
    Shape must be a valid identifier of a living entity.

## Fields

Field | Type | Default | Description
`shape` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The shape to change the player into. If not specified, the player will revert to their original shape.
`nbt` | [NBT](https://origins.readthedocs.io/en/latest/types/data_types/nbt/) | *optional* | Additional NBT data to apply to the shape.
`action_on_success` | [Entity Action Type](../entity.md) | *optional* | Action to perform when the player successfully changes shape.

## Examples

```json
{
  "type": "shappoli:change_shape",
  "shape": "minecraft:fox"
}
```

This example will change the player's shape into a fox.

```json
{
  "type": "shappoli:change_shape",
  "shape": "minecraft:fox",
  "nbt": {
    "Age": -100
  },
  "action_on_success": {
    "type": "apoli:execute_command",
    "command": "say I'm a baby fox!"
  }
}
```

This example will change the player's shape into a baby fox and say "I'm a baby fox!".
