# Set Origin

This action allows you to set the origin of an entity.

Type ID: `shappoli:set_origin`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`layer` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | `origins:origin` | The ID of the origin layer.
`origin` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | | The origin to set.

## Examples

```json
{
  "type": "shappoli:set_origin",
  "layer": "origins:origin",
  "origin": "origins:avian"
}
```

This example sets the origin of the entity to `origins:avian`.
