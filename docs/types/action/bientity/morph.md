# Morph

Morphs an actor player into a target entity.

Type ID: `shappoli:morph`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! warning
    This action only works if the actor is a player, and the target entity is a living entity.

## Fields

Field | Type | Default | Description
`ignore_nbt` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to ignore the NBT data of the target entity. Or copy it to the player.
`action_on_success` | [Bi-entity Action](../bientity.md) | *optional* | The action to perform when the player is successfully morphed.

## Examples

```json
{
  "type": "apoli:action_on_hit",
  "bientity_action": {
    "type": "shappoli:morph"
  }
}

```

This example morphs the player into the target entity when the player hits it.
