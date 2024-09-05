# Suppress Power

This action allows you to suppress a power of another entity.

Type ID: `shappoli:suppress_power`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`power` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The ID of the power to suppress.
`powers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | *optional* | The IDs of the powers to suppress.
`duration` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | | The duration of the suppression in ticks.
`bientity_action` | [Bi-entity Action Type](../action/bientity.md) | *optional* | Action to perform when the power is suppressed.
`ignore_warning` | [Boolean](https://origins.readthedocs.io/en/latest/types/data_types/boolean/) | `false` | Whether to ignore the warning message when the power is probably not supported.

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
