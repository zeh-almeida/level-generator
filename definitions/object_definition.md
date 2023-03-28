# What is an Object

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
