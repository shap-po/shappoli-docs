# Modify Villager Reputation

This power type allows you to modify your reputation with a villager. The more reputation you have, the better trades you can get. See the [Minecraft Wiki](https://minecraft.wiki/w/Villager#Gossiping) for more information on how villager reputation works.

Type ID: `shappoli:modify_villager_reputation`

!!! note
    In the context of this power type, the 'actor' entity is the entity that has the power whilst the 'target' entity is the villager, player is trading with.

!!! info
    This power is basically the same as a [Modify Villager Reputation](https://moborigins.ultrusmods.me/en/latest/power_types/modify_villager_reputation/) power from [Mob Origins](https://modrinth.com/mod/moborigins/) mod.

## Fields

Field | Type | Default | Description
------|------|---------|------------
`bientity_condition` | [Bi-entity Condition Type](../condition/bientity.md) | *optional* | Condition that must be met for the action to trigger.
`modifier` | [Attribute Modifier](https://origins.readthedocs.io/en/latest/types/data_types/attribute_modifier/) | *optional* | The modifier to apply to the reputation.
`modifiers` | [Array](https://origins.readthedocs.io/en/latest/types/data_types/array/) of [Attribute Modifier](https://origins.readthedocs.io/en/latest/types/data_types/attribute_modifier/) | *optional* | The modifiers to apply to the reputation.

## Examples

```json
{
  "type": "shappoli:modify_villager_reputation",
  "modifier": {
    "operation": "addition",
    "value": 100
  }
}
```

This example will add 100 reputation points to a player.
