# Send Action

This action sends a `bientity`/`entity`/`item` action to the specified [Receive Action](../../power/receive_action.md) power.

Type ID: `shappoli:send_action`

!!! note
    This action only supports [Bi-entity Actions](../bientity.md), [Entity Actions](../entity.md), and [Item Actions](../item.md).

## Fields

Field | Type | Default | Description
------|------|---------|------------
`receiver` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | | The ID of the power that will receive the action.

## Examples

See [Receive Action Examples](../../power/receive_action.md#examples) for examples of how to use this action.
