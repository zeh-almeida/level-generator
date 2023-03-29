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

- [•](#width) Width
- [•](#height) Height
- [•](#biome-name) Biome Name
- [•](#room-type-value) Room Type Value

### Width

The `width` of the `room`. It must respect the [maximum](biome_definition.md#maximum-room-size) and [minimum](biome_definition.md#minimum-room-size) requirements of the `biome`.

Should be a `unsigned 8-bit integer` and must be greater than zero. If no value is specified, should use the [biome default size](biome_definition.md#minimum-room-size).

### Height

The `height` of the `room`. It must respect the [maximum](biome_definition.md#maximum-room-size) and [minimum](biome_definition.md#minimum-room-size) requirements of the `biome`.

Should be a `unsigned 8-bit integer` and must be greater than zero. If no value is specified, should use the [biome default size](biome_definition.md#minimum-room-size).

### Biome Name

Identifies the `room`'s [biome](biome_definition.md#what-is-a-biome).

Can never be null nor empty and should match an existing `biome`.

### Room Type Value

Identifies the `room`'s [type](room_type_definition.md#room-types).

Can never be null nor empty and should be valid for the room's current `biome`.
