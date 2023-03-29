| [Previous](levels.md) | [Next](terrain.md) |
| --------------------- | ------------------ |

# Room Generation

Once the tile size and biome are known, the [room](../definitions/room_definition.md#what-is-a-room) can be generated.

Firstly, the `Level Generator` must decide the [room type](../definitions/room_definition.md#what-is-a-room-type), as the room generation is directly influenced by type contraints, such as maximum and minimum sizes, valid orientations, etc.

Secondly, the `Level Generator` must pick a suitable [biome](../definitions/biome_definition.md#what-is-a-biome).

The selection must be aware of the adjacent room, because of biome compatibilities. However, If no biome was selected before, then any biome is valid.

Now that the `Level Generator` is aware of the contraints, it can proceed with the execution:

1. Decide if the room is horizontal or vertical
1. Decide the length and width of the room, in tiles
1. Identify the boundaries between ceiling and floor
1. Determine the amount of objects the room will contain:
   - The total amount cannot exceed the regular 8-bit integer.
   - Each object is given an ID which represents this integer number.
   - [PC](../definitions/object_definition.md#pc-objects) only counts for one room in the whole level.
   - Since every room must have at least one door, one ID must be reserved.
   - Room type and biome could influence the distribution of objects for terrain, items and NPCs.
   - Each object will hold this number as an ID

The object number does not limit any game engine to add more objects to the room, it only influences how many objects the `Level Generator` will process.

Once this variables are known, the `Level Generator` can build the room.

This step can only run once per room.

| [Previous](levels.md) | [Next](terrain.md) |
| --------------------- | ------------------ |
