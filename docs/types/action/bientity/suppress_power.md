# Suppress Power

This action allows you to suppress a power of another entity.

Type ID: `shappoli:suppress_power`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`power` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The ID of the power to suppress. E.g. `my_mod:my_power`.
`powers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The IDs of the powers to suppress.
`power_type` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The type of the power to suppress. E.g. `origins:active_self`.
`power_types` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The types of the powers to suppress.
`power_source` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The ID of the power source to suppress. E.g. `apoli:command`.
`power_sources` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The IDs of the power sources to suppress.
`ignored_power` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The ID of the power to ignore, if it happens to be in any of the previous fields. E.g. `my_mod:my_power`.
`ignored_powers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The IDs of the powers to ignore, if they happen to be in any of the previous fields.
`duration` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | | The duration of the suppression in ticks.
`bientity_action` | [Bi-entity Action Type](../bientity.md) | *optional* | Action to perform when the power is suppressed.
`ignore_no_condition_warning` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to ignore the warning message when the power is probably not supported.
`ignore_multiple_power_warning` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to ignore the warning message when trying to suppress a power of a type `apoli:multiple`.

## Examples

```json
{
  "type": "apoli:multiple",

  "suppressor": {
    "type": "apoli:action_on_block_place",
    "entity_action": {
      "type": "apoli:selector_action",
      "selector": "@s",
      "bientity_action": {
        "type": "shappoli:suppress_power",
        "power": "*:*_power_hit",
        "powers": [
          "*:*_power_active"
        ],
        "duration": 40,
        "bientity_action": {
          "type": "apoli:actor_action",
          "action": {
            "type": "apoli:execute_command",
            "command": "say Suppressed"
          }
        }
      }
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
  },

  "power_active": {
    "type": "apoli:active_self",
    "key": "key.attack",
    "entity_action": {
      "type": "apoli:execute_command",
      "command": "say Active"
    }
  }
}
```

This example will suppress otherwise active powers for 40 ticks (2 seconds) when the player places a block.
