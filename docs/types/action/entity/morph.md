# Morph

Morphs a player into a different entity.

Type ID: `shappoli:morph`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! warning
    This action only works on players.
    Shape must be a valid identifier of a living entity.

## Fields

Field | Type | Default | Description
`shape` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The shape to morph the player into. If not specified, the player will be morphed into their original shape.
`nbt` | [NBT](https://origins.readthedocs.io/en/latest/types/data_types/nbt/) | *optional* | Additional NBT data to apply to the morphed entity.
`action_on_success` | [Entity Action Type](../entity.md) | *optional* | Action to perform when the player is successfully morphed.

## Examples

```json
{
  "type": "shappoli:morph",
  "shape": "minecraft:fox"
}
```

This example morphs the player into a fox.

```json
{
  "type": "shappoli:morph",
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

This example morphs the player into a baby fox and displays a message in chat.
