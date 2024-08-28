# Holder

The holder condition checks if the entity holding the item meets the specified condition.

Type ID: `shappoli:holder`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`condition` | [Entity Condition Type](../entity.md) | | Condition that must be met for the action to trigger. If not specified, the condition will always trigger.

## Examples

```json
"item_condition": {
  "type": "shappoli:holder",
  "condition": {
    "type": "apoli:moving"
  }
}
```

This example checks if the entity holding the item is moving.
