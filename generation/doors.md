# Door/Corridor Placements

[Doors and corridors](../definitions/object_definition.md#door-objects) are placed in a [room](../definitions/room_definition.md#what-is-a-room) in order to connect it to a neighboring room.

Each and every item must be accessible by the [PC objects](../definitions/object_definition.md#pc-objects).
In order to do so, the door/corridor must be placed on a tile that has an adjacent free tiles the same height of the object next to it and their reference tile must be always connected to a floor surface.

For example:

Given a door that is two tiles high and one tile across, palce it at the leftmost corner of the room.

In order to have this door accessible, a two tile-high, one tile-long space must exist at the right of this door.

Doors and corridors must respect the final number of objects in the room.
