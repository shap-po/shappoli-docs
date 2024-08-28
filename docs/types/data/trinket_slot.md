# Trinket Slot

A trinket slot is a slot where trinkets can be equipped. This is used in powers that interact with trinkets.


!!! note
    This data type is useless without [Trinkets](https://modrinth.com/mod/trinkets/) installed.

!!! note
    See [Trinkets Documentation](https://github.com/emilyploszaj/trinkets/wiki/Default-Slots) for a list of default trinket slots.
    Value before the slash is the group, value after the slash is the name.
    E.g. `chest/necklace` is the `necklace` slot in the `chest` group.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`group`| [String](https://origins.readthedocs.io/en/latest/types/data_types/string/) | *optional* | The group of the slot.
`name` | [String](https://origins.readthedocs.io/en/latest/types/data_types/string/) | *optional* | The name of the slot.
`index` | [Integer](https://origins.readthedocs.io/en/latest/types/data_types/integer/) | *optional* | The index of the slot.

## Examples

```json
{
  "group": "chest",
  "name": "necklace",
  "index": 0
}
```

This would represent the first slot in the `chest` group, named `necklace`.

```json
{
  "group": "chest"
}
```

This would represent any slot in the `chest` group (`chest/necklace`, `chest/cape`, `chest/back`, etc.).

```json
{
  "name": "glove"
}
```

This would represent any slot named `glove` in any group (`hand/glove`, `offhand/glove`, etc.).

```json
{
  "index": 0
}
```

This would represent the `first` slot in any group.

```json
{}
```

This would represent any slot.

I think you get the idea.
