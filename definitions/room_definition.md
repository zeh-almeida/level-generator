# What is a Room

A `Room` is a collection of [tiles](tile_definition.md#what-is-a-tile) arranged in a horizontal or vertical manner.

It has at least one connection to another room, either directly or using a connector.

Rooms have [biomes](biome_definition.md#what-is-a-biome) which defines some characteristics for what happens inside the room.

Rooms must have a single biome.

Rooms can have [objects](object_definition.md#what-is-an-object) placed on them such as doors, items, traps, etc.
However, items must be placed on tiles and there is a limit of available tiles per room.

Rooms must define the height in which the ceiling starts and ends.

Rooms must define the height in which the floor starts and ends.

Rooms must also have a single [type](room_definition.md#what-is-room-type).

## What is a Room Type

While most rooms are about exploration, some rooms are key to the level.
For example:

- [Boss Rooms](#boss-rooms)
- [Savepoints](#savepoints)
- [Item givers](#item-givers)
- [Links](#links)

Based on the type, a room be generated with different expectations.

### Boss Rooms

Must contain a boss-type [object](object_definition.md#what-is-an-object).
Those types of room have a greater range of customization because it must allow for boss movements, which are generally different from other NPCs or even the PC.

### Savepoints

Must contain a savepoint-type [object](object_definition.md#what-is-an-object).
Rooms of this type are generally small and should not contain harmful objects.

### Item givers

Must contain a item-type [object](object_definition.md#what-is-an-object).
Rooms of this type are generally used to advance the plot by giving the PC a new ability.

### Links

Must connect one room to another. Its [biome](biome_definition.md#what-is-a-biome) must be neutral between rooms.
It has no restrictions on [Object Types](object_definition.md#object-types).
