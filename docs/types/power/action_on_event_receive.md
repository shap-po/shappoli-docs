# Action On Event Receive

This action is triggered when the player receives an event from the [Send Event](../action/meta/send_event.md) action.

Type ID: `shappoli:action_on_event_receive`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`action` | [Entity Action Type](../action/entity.md) | *optional* | Action to perform when ANY event is received and it passes the condition.
`bientity_action` | [Bi-entity Action Type](../action/bientity.md) | *optional* | Action to perform when a bientity event is received.
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition that must be met for the action to trigger.
`entity_action` | [Entity Action Type](../action/entity.md) | *optional* | Action to perform when an entity event is received.
`entity_condition` | [Entity Condition Type](../condition/entity.md) | *optional* | Condition that must be met for the action to trigger. This condition is different from the `condition` field, that disables the power entirely.
`item_action` | [Item Action Type](../action/item.md) | *optional* | Action to perform when an item event is received.
`item_condition` | [Item Condition Type](../condition/item.md) | *optional* | Condition that must be met for the action to trigger.

## Examples

```json
{
  "type": "apoli:multiple",

  "receiver": {
    "type": "shappoli:action_on_event_receive",
    "action": {
      "type": "apoli:execute_command",
      "command": "say Received an event"
    },
    "bientity_action": {
      "type": "apoli:actor_action",
      "action": {
        "type": "apoli:execute_command",
        "command": "say Received a bientity event"
      }
    },
    "entity_action": {
      "type": "apoli:execute_command",
      "command": "say Received an entity event"
    },
    "item_action": {
      "type": "apoli:holder_action",
      "action": {
        "type": "apoli:execute_command",
        "command": "say Received an item event"
      }
    }
  },

  "sender_1": {
    "type": "apoli:action_on_item_use",
    "item_action": {
      "type": "shappoli:send_event",
      "receiver": "*:*_receiver"
    },
    "entity_action": {
      "type": "shappoli:send_event",
      "listener": "*:*_receiver"
    }
  },

  "sender_2": {
    "type": "apoli:action_on_hit",
    "bientity_action": {
      "type": "shappoli:emit_event",
      "receiver": "*:*_receiver"
    }
  }
}
```

In this example, `receiver` will receive events from the [Send Event](../action/meta/send_event.md) action and send messages based on the event type.
`sender_1` and `sender_2` will send different types of events to the receiver.
