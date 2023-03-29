| [Previous](tiles.md) | [Next](rooms.md) |
| -------------------- | ---------------- |

# Level Constraints

A [level](../definitions//level_definition.md#what-is-a-level) must define how many rooms are expected to be generated. This number does not need to be fixed, it can also be provided as a minimum-maximum value.

This allows the `Level Generator` to have more freedom of choice for rooms.

## Constraints

## Amount of Biomes

The number of [biomes](../definitions/biome_definition.md#what-is-a-biome) available for generation must be greater or equal to `3`.

The available biomes must be distinct and if possible, should have their affinities declared, as this allows for a more varied result.

### Amount of Rooms

The number of [rooms](../definitions/room_definition.md#what-is-a-room) must be represented by a `unsigned 8-bit integer` and the minimum value must be equal or greater than `4`.

This value must be provided from the environment. If not supplied, assume the default value.

### Room Types

Regardless of how many `rooms` there are in a `level`, the following `room types` must be used at least once:

- [•](../definitions/room_type_definition.md#savepoints) Savepoint
- [•](../definitions/room_type_definition.md#boss-rooms) Boss Room
- [•](../definitions/room_type_definition.md#regular-room) Regular Room

This ensures the generated `level` is usable for an adventure.

### Objects

The `Level Generator` must have at least `1` of each of the following [objects](../definitions/object_definition.md#what-is-an-object) available in order to complete its process:

- [•](../definitions/object_type_definition.md#pc-objects) Player Character
- [•](../definitions/object_type_definition.md#boss-objects) Boss
- [•](../definitions/object_type_definition.md#items-objects) Item

Those `objects` grant a use for exploration and objective to the result of the process.

| [Previous](tiles.md) | [Next](rooms.md) |
| -------------------- | ---------------- |
