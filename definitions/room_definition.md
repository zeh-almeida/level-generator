| [Definitions](README.md) |
| ------------------------ |

# Rooms

## What is a Room

A `Room` is a collection of [tiles](tile_definition.md#what-is-a-tile) arranged in a horizontal or vertical manner.

It has at least one connection to another room, either directly or using a connector.

Rooms have a [biome](biome_definition.md#what-is-a-biome) which defines some characteristics for what happens inside the room. The biome is not unique to the room, it can be shared with other rooms in the level but every room has one.

Rooms must also have a single [type](room_type_definition.md#what-is-room-type) in order to help with placement and other characteristics and limitations.

Rooms can have [objects](object_definition.md#what-is-an-object) placed on them such as doors, items, traps, etc.
However, items must be placed on tiles and there is a limit of available tiles per room.

## Properties

`Rooms` have a set of properties, some of which have default values.
All of them are required.

- [•](#generation-number) Generation Number
- [•](#width) Width
- [•](#height) Height
- [•](#biome-name) Biome Name
- [•](#room-type-value) Room Type Value
- [•](#set-of-objects) Set of Objects

### Generation Number

The number of the `room` in the `level`. This is a sequential number used to distinguish generational order to sort `rooms` easier.

Must be unique across other `rooms` in order to avoid conflicts.

### Width

The `width` of the `room`. It must respect the [maximum](biome_definition.md#maximum-room-size) and [minimum](biome_definition.md#minimum-room-size) requirements of the `biome`.

Should be a `unsigned 16-bit integer` and must be greater than zero. If no value is specified, should use the [biome default size](biome_definition.md#minimum-room-size).

The area of the `room` ([width](#width) times [height](#height))must fall between the [maximum room size](biome_definition.md#maximum-room-size) and [minimum room size](biome_definition.md#minimum-room-size) for the `biome`.

### Height

The `height` of the `room`. It must respect the [maximum](biome_definition.md#maximum-room-size) and [minimum](biome_definition.md#minimum-room-size) requirements of the `biome`.

Should be a `unsigned 16-bit integer` and must be greater than zero. If no value is specified, should use the [biome default size](biome_definition.md#minimum-room-size).

The area of the `room` ([width](#width) times [height](#height))must fall between the [maximum room size](biome_definition.md#maximum-room-size) and [minimum room size](biome_definition.md#minimum-room-size) for the `biome`.

### Biome Name

Identifies the `room`'s [biome](biome_definition.md#what-is-a-biome).

Can never be null nor empty and should match an existing `biome` [name](biome_definition.md#name).

### Room Type Value

Identifies the `room`'s [type](room_type_definition.md#room-types).

Can never be null nor empty and should be valid for the room's current `biome`.

### Set of Objects

List of [objects](object_definition.md#what-is-an-object) placed in this room.
Can never be null but can be empty.

Multiple copies of an `object` can be placed in the `room` but their
[Anchor Tile](object_definition.md#anchor-tile),
[Width](object_definition.md#width),
[Height](object_definition.md#height)
and [Direction](object_definition.md#direction)
properties must not overlap.

The set of `objects` cannt store more items than the maximum value of a `unsigned 8-bit integer`: `255` objects in total.

| [Definitions](README.md) |
| ------------------------ |
