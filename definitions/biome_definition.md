# What is a Biome

`Biomes` define the type of content you expect in a [room](room_definition.md#what-is-a-room).

For example, in a `savana` biome you are likely to expect plants, animals, and objects related to this area.

In a `winter` biome, it is reasonable to expect a snowy setting with flora and fauna matching it.

Biomes can define a [Affinity](#affinity) between them, such as to encourage or disencourage connections.

For example: `magma` and `forest` biomes have negative affinity. This means rooms with those biomes cannot be linked directly.

The `mountain` biome however has a neutral affinity to both `magma` and `forest` biomes so `mountain` can be used in a room in order to bridge between those two.

## Affinity

Affinity defines how `biomes` can be connected. There are three types of affinity:

- [Positive](#positive-affinity)
- [Negative](#negative-affinity)
- [Neutral](#neutral-affinity)

Affinity is a relationship exclusevely between two different biomes. If an affinity is not defined, it must be considered neutral.

### Positive Affinity

`Biomes` with positive affinity have a greater chance to be connected directly to one another.

This hints the `Level Generator` when processing adjacent rooms to prefer higher affinities, meaning the chance to pick a favorable biome is higher. The `Level Generator` may still pick a biome with neutral or negative affinities.

### Negative Affinity

`Biomes` with negative affinity must never be connected directly to one another.

This hints the `Level Generator` when processing adjacent rooms to have a connecting room between these two biomes.

Conections must be formed by a [neutral](#neutral-affinity) biome between the negative ones.

### Neutral Affinity

`Biomes` with neutral affinity can be used to connect to any biome.

They are specially useful to connect biomes with [negative affinity](#negative-affinity).
