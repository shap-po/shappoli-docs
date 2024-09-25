# Suppress Power (Power Type)

This power allows you to completely disable another power of the same entity.

Type ID: `shappoli:suppress_power`

!!! not
    This power only works on powers that have a `condition` field.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`power` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The ID of the power to suppress. E.g. `my_mod:my_power`.
`powers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The IDs of the powers to suppress.

## Examples

```json
{
  "type": "apoli:multiple",

  "suppressor": {
    "type": "shappoli:suppress_power",
    "power": "*:*_power_hit",
    "condition": {
      "type": "apoli:sneaking"
    }
  },

  "power_hit": {
    "type": "apoli:action_on_hit",
    "bientity_action": {
      "type": "apoli:actor_action",
      "action": {
        "type": "apoli:execute_command",
        "command": "say Hit"
      }
    }
  }
}
```

This example prevents the power `*:*_power_hit` from triggering if the entity is sneaking.
