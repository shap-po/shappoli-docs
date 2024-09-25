# Action On Shape Change

This power type allows you to perform actions when the player changes their shape.

Type ID: `shappoli:action_on_shape_change`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the shape that the actor changed into. If the player is changing their shape back to their original form, 'actor' and 'target' will be the same entity.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_action` | [Bi-entity Action Type](../action/bientity.md) | | Action to perform when a shape change is detected.
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition that must be met for the action to trigger.

## Examples

```json
{
  "type": "shappoli:action_on_shape_change",
  "bientity_action": {
    "type": "apoli:and",
    "actions": [
      {
        "type": "apoli:actor_action",
        "action": {
          "type": "apoli:execute_command",
          "command": "say I just changed shape!"
        }
      },
      {
        "type": "apoli:target_action",
        "action": {
          "type": "apoli:execute_command",
          "command": "say I was changed shape into!"
        }
      }
    ]
  }
}
```

This example will execute two commands when the player changes their shape.

```json
{
  "type": "shappoli:action_on_shape_change",
  "bientity_action": {
    "type": "apoli:target_action",
    "action": {
      "type": "apoli:execute_command",
      "command": "data modify entity @s Age set value -20"
    }
  },
  "bientity_condition": {
    "type": "apoli:target_condition",
    "condition": {
      "type": "apoli:entity_type",
      "entity_type": "minecraft:villager"
    }
  }
}
```

This example will make it so the player will always be a baby villager when they change into a villager.
