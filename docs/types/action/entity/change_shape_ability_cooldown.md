# Change Shape Ability Cooldown

Changes the cooldown of the player's shape ability. Works similarly to the [Change Resource](https://origins.readthedocs.io/en/latest/types/entity_action_types/change_resource/) action.

Type ID: `shappoli:change_shape_ability_cooldown`

!!! note
    This action requires [Woodwalkers](https://modrinth.com/mod/woodwalkers) to be installed.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`change` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | | The amount to change the cooldown by.
`operation` | [String](https://origins.readthedocs.io/en/latest/types/data_types/string/) | `"add"` | Determines if the action should add or set the value of the resource. Accepts `"add"` or `"set"`.

## Examples

```json
{
  "type": "shappoli:change_shape_ability_cooldown",
  "change": 1,
  "operation": "add"
}
```

This example will add `1` to the player's shape ability cooldown.
