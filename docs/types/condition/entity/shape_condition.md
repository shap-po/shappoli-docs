# Shape Condition

This conditions allows you to check conditions on the shape of the player.

Type ID: `shappoli:shape_condition`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this condition, the 'actor' entity is the entity that has the power whilst the 'target' entity is the actor's shape. If the player is in their original form, 'actor' and 'target' will be the same entity.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_condition` | [Bi-entity Condition Type](../../condition/bientity.md) | | Condition to check on the shape.

## Examples

```json
{
  "type": "shappoli:shape_condition",
  "bientity_condition": {
    "type": "apoli:equal"
  }
}
```

This example will check if the entity is in its original form.

```json
{
  "type": "shappoli:shape_condition",
  "bientity_condition": {
    "type": "apoli:target_condition",
    "condition": {
      "type": "apoli:entity_type",
      "entity_type": "minecraft:villager"
    }
  }
}
```

This example will check if the entity is in the shape of a villager.
