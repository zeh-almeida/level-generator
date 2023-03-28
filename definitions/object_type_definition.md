# Object Types

`Objects types` define how [objects](object_definition.md#what-is-an-object) interact with the environment and the room they are located.

Currently the known types are:

- [•](#trap-objects) Traps
- [•](#door-objects) Doors
- [•](#boss-objects) Boss
- [•](#npc-objects) NPC
- [•](#pc-objects) Player Characters
- [•](#item-objects) Items
- [•](#terrain-objects) Terrain features

## Trap Objects

Objects that cause harm to the PC.
Examples are: Spiked, falling boulders, etc.

Trap objects do not allow for stacked objects.
This means that if the object is placed on the ground, no other object can be placed within the ground bounds on top the object.

The same applies in the ceiling: if the object is placed there, no other object can be placed directly under this object until the ceiling limit is met.

This type cannot be stacked.

## Door Objects

Object used to enter or exit a room.

Only one door can be placed at a wall at a time.

This means a rectangular room can have a maximum of four doors.
No room can have less than one door.

Doors may not be physically present but only an indication of room change, like a corridor.

This type cannot be stacked.

## Boss Objects

Specialization of the [NPC type](#npc-objects).

This type cannot be stacked.

## NPC Objects

Represents movable interactable objects in the [room](room_definition.md#what-is-a-room).

NPCs can move but cannot exit the room they are in.

They can also interact with other objects but the objects are responsible for handling NPC activity own their own.

NPCs can be friendly to [PCs](#pc-objects) or not, it is not important to the room definition but can be useful for planning the room disposition.

This type can be stacked: it is possible to have two NPCs occupy the same place inside the room. Their interaction as objects is not handled by the `Level Generator`, it is only mentioned to help with room placement.

## PC Objects

Represents a Player Character. While a PC is very siumilar to a [NPC](#npc-objects), it is not bound to a room, being able to move between rooms as it wishes.

It can interact with other objects and those objects are responsible to define how the interaction is resolved.

It can also be stacked: it is possible to have two PCs occupy the same place inside the room. Their interaction as objects is not handled by the `Level Generator`, it is only mentioned to help with room placement.

## Items Objects

Objects that the [PCs](#pc-objects) or [NPCs](#npc-objects) can interact with. Those object do not change the disposition of the room but may allow the characters to improve their interaction with the world.

Examples include `keys`, `health items`, `weapons`, etc.

It is necessary to have those items described for the `Level Generator` because they can be placed in a optimal way.

Objects of this type can be stacked.

The room generation does not care about drop rates because this is a behavior defined in an object. The `Level Generator` only cares about objects which are placed in the room directly.

## Terrain Objects

This type defines a structure in the room which affects how the room behaves.

Normally, the room is just a box, either horizontal ou vertical.

Terrain objects allows the `Level Generator` to add `platforms`, `slopes`, `ramps`, etc to the environment, changing how the room interacts with neighboors.

Terrain does not need to be rectangular as the rooms. They may be diagonal as well and their definition must make this clear.

Terrain objects must always define their start and end tiles. This allows the `Level Generator` to place other objects regarding the terrain limitations.

### Example

If a slope has a `height of 2 tiles`, a [door](#door-objects) cannot the opened if it stays directly behind this slope. Therefore, the `Level Generator` must change the door placement to be on top of the slope.
