# Shape Action

Executes an action on the player's shape.

Type ID: `shappoli:shape_action`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this condition, the 'actor' entity is the entity that has the power whilst the 'target' entity is the actor's shape. If the player is in their original form, 'actor' and 'target' will be the same entity.

## Fields

Field | Type | Default | Description
`bientity_action` | [Bi-entity Action Type](../../action/bientity.md) | | Action to execute on the shape.

## Examples

```json
{
  "type": "shappoli:shape_action",
  "bientity_action": {
    "type": "apoli:target_action",
    "action": {
      "type": "apoli:execute_command",
      "command": "data modify entity @s Age set value -1"
    }
  }
}
```

This example will turn player's shape into a baby.
