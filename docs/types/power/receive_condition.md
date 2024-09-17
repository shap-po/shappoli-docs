# Receive Condition

This power allows you to receive a `bientity`/`entity`/`item` condition context from a specified [Send Condition](../condition/meta/send_condition.md) condition, check it, and return the result back to the sender.

Type ID: `shappoli:receive_condition`

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition to check when a bientity condition context is received.
`entity_condition` | [Entity Condition Type](../condition/entity.md) | *optional* | Condition to check when an entity condition context is received.
`item_condition` | [Item Condition Type](../condition/item.md) | *optional* | Condition to check when an item condition context is received.

## Examples
