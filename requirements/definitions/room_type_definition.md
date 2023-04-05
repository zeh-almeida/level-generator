| [Definitions](README.md) |
| ------------------------ |

# Room Types

## What is a Room Type

While most rooms are about exploration, some rooms have special characteristics to the level.

For example:

- [•](#boss-rooms) Boss Rooms
- [•](#savepoints) Savepoints
- [•](#item-givers) Item givers
- [•](#links) Links
- [•](#regular-room) Regular Room

Based on the type, a room be generated with different expectations.

## Available Types

### Boss Rooms

Must contain a boss-type [object](object_definition.md#what-is-an-object).
Those types of room have a greater range of customization because it must allow for boss movements, which are generally different from other NPCs or even the PC.

### Savepoints

Must contain a savepoint-type [object](object_definition.md#what-is-an-object).
Rooms of this type are generally small and should not contain harmful objects.

### Item Givers

Must contain a item-type [object](object_definition.md#what-is-an-object).
Rooms of this type are generally used to advance the plot by giving the PC a new ability.

### Links

Must connect one room to another. The connection room's [biome](biome_definition.md#what-is-a-biome) must be neutral between rooms.
It has no restrictions on [Object Types](object_definition.md#object-types).

### Regular Room

Has no special characteristic. No restrictions for [object](object_definition.md#what-is-an-object) placement.

## Properties

A `room type` is an `enum` value.

As for now, it can be represented completely as a `unsigned 4-bit integer`.

It should be represented as:

- `0`: [Regular Room](#regular-room)
- `1`: [Link](#links)
- `2`: [Savepoint](#savepoints)
- `3`: [Item Giver](#item-givers)
- `4`: [Boss Room](#boss-rooms)

| [Definitions](README.md) |
| ------------------------ |
