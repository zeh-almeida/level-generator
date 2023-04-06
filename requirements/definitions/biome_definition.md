| [Definitions](README.md) |
| ------------------------ |

# What is a Biome

`Biomes` define the type of content you expect in a [room](room_definition.md#what-is-a-room).

For example, in a `savana` biome you are likely to expect plants, animals, and objects related to this area.

In a `winter` biome, it is reasonable to expect a snowy setting with flora and fauna matching it.

Biomes can define a [Affinity](#affinity) between them, such as to encourage or disencourage connections.

For example: `magma` and `forest` biomes have negative affinity. This means rooms with those biomes cannot be linked directly.

The `mountain` biome however has a neutral affinity to both `magma` and `forest` biomes so `mountain` can be used in a room in order to bridge between those two.

## Affinity

Affinity defines how `biomes` can be connected. There are three types of affinity:

- [•](#positive-affinity) Positive
- [•](#negative-affinity) Negative
- [•](#neutral-affinity) Neutral

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

## Properties

`Biomes` have a set of properties, some of which have default values.
All of them are required.

- [•](#name) Name
- [•](#maximum-room-size) Maximum Room Size
- [•](#minimum-room-size) Minimum Room Size
- [•](#affinity-map) Affinity Map

### Name

Name of the `biome`, used to identify it when running the `Level Generator`. Must be unique across other `biomes` in order to avoid conflicts.

Should be a `string` in `UTF-8` encoding, up to `50` characters.
Cannot be null nor empty.

### Maximum Room Size

Especifies that any `room` with this `biome` cannot have its height nor length be longer than this value.

The default value is the `(current tile size) * 2`.

Should be a `unsigned 16-bit integer`, must be greater than zero or default. Cannot be less than [the minimum room size](#minimum-room-size).

### Minimum Room Size

Especifies that any `room` with this `biome` cannot have its height nor length be less than this value.

The default value is the `(current tile size) * 2`.

Should be a `unsigned 16-bit integer`, must be greater than zero or default. Cannot be greater than [the maximum room size](#maximum-room-size).

### Affinity Map

Relation of `biome name` and `affinity` value for the current `biome`.

This allows the `Level Generator` to easily check affinity values with the `biome`.

If a `biome name` is not found in this map, it should consider the biome with `neutral affinity`.

It can be empty but not null. If empty, it is neutral to all other `biomes`.

#### Example

The biome `Forest` has the following `Afinity Map`:

- `Mountain` with `Positive Affinity`
- `Lake` with `Positive Affinity`
- `Cave` with `Positive Affinity`
- `Desert` with `Negative Affinity`
- `Volcano` with `Negative Affinity`

If the `Level Generator` tries to match the `Praire` biome to the `Forest` biome, the result should be `Neutral Affinity` because `Forest` biome didn't specify a relationship.

`Praire` could also have an `Affinity Map` specifying this relationship with `Forest`, which could change the outcome, but not for this example.

#

| [Definitions](README.md) |
| ------------------------ |
