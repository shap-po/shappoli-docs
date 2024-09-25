# Copy Origin

This action allows you to copy origins from one entity to another.

Type ID: `shappoli:copy_origin`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`layer` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | `origins:origin` | The ID of the origin layer.
`modify_actor` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to modify the actor's origin.
`modify_target` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `true` | Whether to modify the target's origin.

## Examples

```json
{
  "type": "shappoli:copy_origin",
  "layer": "origins:origin",
  "modify_actor": true,
  "modify_target": true
}
```

This example will swap the origins of the actor and the target.
