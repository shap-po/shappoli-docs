# Action On Shape Ability Use

This power type allows you to perform actions when the player uses their shape ability.

Type ID: `shappoli:action_on_shape_ability_use`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the actor's shape. If the player is in their original form, 'actor' and 'target' will be the same entity.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_action` | [Bi-entity Action Type](../action/bientity.md) | | Action to perform when a shape ability use is detected.
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition that must be met for the action to trigger.

## Examples

```json
{
  "type": "shappoli:action_on_shape_ability_use",
  "bientity_action": {
    "type": "apoli:and",
    "actions": [
      {
        "type": "apoli:actor_action",
        "action": {
          "type": "apoli:execute_command",
          "command": "say I just used my shape ability!"
        }
      },
      {
        "type": "apoli:target_action",
        "action": {
          "type": "apoli:execute_command",
          "command": "say I was used shape ability as!"
        }
      }
    ]
  }
}
```

This example will execute two commands when the player uses their shape ability.
