# Action On Entity Collision

This action is triggered when the entity collides with another entity.

Type ID: `shappoli:action_on_entity_collision`

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the entity that the actor collides with.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_action` | [Bi-entity Action Type](../action/bientity.md) | | Action to perform when a collision occurs.
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition that must be met for the action to trigger.
`cooldown`| [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | `1` | Interval of ticks this power needs to recharge before the power can be triggered again.
`hud_render` | [Hud Render](https://origins.readthedocs.io/en/latest/types/data_types/hud_render/) | `{"should_render": false}` | Determines how the cooldown of this power is visualized on the HUD.

## Examples

```json
{
  "type": "shappoli:action_on_entity_collision",
  "bientity_condition": {
    "type": "apoli:target_condition",
    "condition": {
     "type": "apoli:living"
    }
  },
  "bientity_action": {
    "type": "apoli:damage",
    "amount": 1,
    "damage_type": "minecraft:mob_attack"
  }
}
```

This example power will damage every entity that comes in contact with you.
