# Prevent Shape Change

Prevents the player from changing their shape.

Type ID: `shappoli:prevent_shape_change`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the shape that the actor is trying to change into. If the player is changing their shape back to their original form, 'actor' and 'target' will be the same entity.

!!! note
    This power will not prevent the player from changing their shape with commands or [Change Shape (Bi-entity Action)](../action/bientity/change_shape.md) and [Change Shape (Entity Action)](../action/entity/change_shape.md) actions.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | If specified, the shape change will only be prevented if this condition is met.

## Examples

```json
{
  "type": "shappoli:prevent_shape_change"
}
```

This example will completely prevent the player from changing their shape.

```json
{
  "type": "shappoli:prevent_shape_change",
  "bientity_condition": {
    "type": "apoli:target_condition",
    "condition": {
      "type": "apoli:entity_type",
      "entity_type": "minecraft:villager"
    }
  }
}
```

This example will prevent the player from changing their shape into a villager.
