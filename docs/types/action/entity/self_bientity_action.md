# Self Bientity Action

Runs a `bientity` action with the actor and target being the same entity.

Type ID: `shappoli:self_bientity_action`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`action` | [Bi-entity Action Type](../bientity.md) | | Action to perform.

## Examples

```json
{
  "type": "shappoli:self_bientity_action",
  "action": {
    "type": "apoli:damage"
  }
}
```

This example damages makes the entity damage itself.
