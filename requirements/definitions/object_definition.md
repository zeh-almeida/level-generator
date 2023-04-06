| [Definitions](README.md) |
| ------------------------ |

# Objects

## What is an Object

`Objects` are items placed in a room.
They can be traps, doors, secrets, NPCs, etc.

Objects may have conditions to be placed, such as:

- only on ground
- only on ceiling
- ceiling or ground

They can also alter the tile they reside in, like spikes or holes.

From a level generation perspective, objects are not going to be handled by the `Level Generator` but must be taken into consideration in order to be correctly accomodated.

The only time objects are relevant for the level generation process is when linking specifing doors, walkways or shafts from one room to another.

Objects can have a trigger specified. At this moment, the `Level Generator` will not care about those triggers.

Objects must define how many tiles they occupy and if they should be placed inside the tile, on top or bottom.

Every object must have an anchor tile in order for the `Level Generator` to be able to calculate its placement.

Objects must also declare their [type](object_type_definition.md#object-types) in order for the `Level Generator` to access their constraints.

## Example

Spikes occupy two horizontal and two vertical tiles.
They must be placed inside the tile they are anchored to and cannot have objects on top of them.

## Properties

`Objects` have a set of properties. Some are required and other are optional.

- [•](#object-id) Object ID
- [•](#direction) Direction
- [•](#width) Width
- [•](#height) Height
- [•](#object-type) Object Type
- [•](#anchor-tile) Anchor Tile

### Object ID

Value is never null nor empty.
Value is generated when the `object` definition is registered in the `Level Generator`.

Must be unique across other `objects` in order to avoid conflicts, must be represented as a `unsigned 16-bit integer` value and must be greater than zero.

### Direction

Value is never null nor empty.
Direction is used to place the object from the [Anchor Tile](#anchor-tile) into the especified direction.

Must be a `1-bit` value, representing `Up` or `Down`.

#### Example

Object `example` has a length of `2 tiles` and a height of `3 tiles`.
Its direction is `Up`.

The `Level Generator` must read the `example` object as a floor object, since it is has an upwards direction.

### Width

Value is never null nor empty, must always be greater than `0`.
Default value is `1`.

Must be a `unsigned 4-bit integer`.

Defines how wide the object is in tiles.

Objects that are wider than the room cannot be placed.

### Height

Value is never null nor empty, must always be greater than `0`.
Default value is `1`.

Must be a `unsigned 4-bit integer`.

Defines how tall the object is in tiles.

Objects that are taller than the room cannot be placed.

### Object Type

An `Object` must have a single [object Type](object_type_definition.md#object-types). It can never be null nor empty.

### Anchor Tile

`Tile` in the `room` used as a source point for the `object`. This marks the `0:0` coordinate of the `object`.

#

| [Definitions](README.md) |
| ------------------------ |
