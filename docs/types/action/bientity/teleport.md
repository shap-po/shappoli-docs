# Teleport

Teleports / swaps the position of two entities.

Type ID: `shappoli:teleport`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`teleport_actor` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to teleport the actor entity to the target entity's position.
`teleport_target` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `true` | Whether to teleport the target entity to the actor entity's position.
`rotate` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to also modify the rotation of the entities.

## Examples

```json
{
  "type": "shappoli:teleport"
}
```

This example teleports the target entity to the actor entity's position.

```json
{
  "type": "shappoli:teleport",
  "teleport_actor": true,
  "teleport_target": true,
  "rotate": true
}
```

This example swaps the positions of two entities, and switches their head rotations.
