# Is Trinket

Checks if the item is a trinket.

Type ID: `shappoli:is_trinket`

!!! note
    This condition requires [Trinkets](https://modrinth.com/mod/trinkets/) to be installed.

!!! warning
    This condition only works with modded items that are registered as trinkets.
    If you want to check if the item can be equipped in a trinket slot, use the [`shappoli:equippable_trinket`](./equippable_trinket.md) condition instead.

## Fields

None.

## Examples

```json
"condition": {
  "type": "shappoli:is_trinket"
}
```

This example will check if the item is registered as a trinket.