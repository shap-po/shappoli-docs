# Prevent Shape Ability Use

Prevents the player from using their shape ability.

Type ID: `shappoli:prevent_shape_ability_use`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the actor's shape. If the player is in their original form, 'actor' and 'target' will be the same entity.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | If specified, the shape ability use will only be prevented if this condition is met.

## Examples

```json
{
  "type": "shappoli:prevent_shape_ability_use"
}
```

This example will completely prevent the player from using their shape ability.

```json
{
  "type": "shappoli:prevent_shape_ability_use",
  "bientity_condition": {
    "type": "apoli:target_condition",
    "condition": {
      "type": "apoli:entity_type",
      "entity_type": "minecraft:blaze"
    }
  }
}
```

This example will prevent the player from using their shape ability when they are in the shape of a blaze.
