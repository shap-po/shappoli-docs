# Send Event

This action sends a `bientity`/`entity`/`item` to the specified [Action On Event Receive](../../power/action_on_event_receive.md) power.

Type ID: `shappoli:send_event` or `shappoli:emit_event`

!!! note
    This action does not support [Block Actions](../block.md).

## Fields

Field | Type | Default | Description
------|------|---------|------------
`receiver` \| `listener` | [Identifier](https://origins.readthedocs.io/en/latest/types/data_types/identifier/) | | The ID of the power that will receive the event.

## Examples

See [Action On Event Receive](../../power/action_on_event_receive.md#examples) for examples of how to use this action.
