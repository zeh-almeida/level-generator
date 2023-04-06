| [Previous](levels.md) | [Next](terrain.md) |
| --------------------- | ------------------ |

# Room Generation

Once the [tile size](tiles.md) and [biome](levels.md) are available to the `level Generator`, the [rooms](../definitions/room_definition.md#what-is-a-room) can be processed.

Firstly, the `Level Generator` must decide the [room type](../definitions/room_definition.md#what-is-a-room-type), as the room generation is directly influenced by type contraints, such as maximum and minimum sizes, valid orientations, etc.

The following `room types` must be used at least once when generating `rooms`:

- [•](../definitions/room_type_definition.md#savepoints) Savepoint
- [•](../definitions/room_type_definition.md#boss-rooms) Boss Room
- [•](../definitions/room_type_definition.md#regular-room) Regular Room

Secondly, the `Level Generator` must pick a suitable [biome](../definitions/biome_definition.md#what-is-a-biome).

The selection must be aware of the adjacent room, because of biome compatibilities. However, If no biome was selected before, then any biome is valid.

Now that the `Level Generator` is aware of the contraints, it can proceed with the execution:

1. Decide if the `room` is horizontal or vertical
1. Decide the [height](../definitions/room_definition.md#height) and [width](../definitions/room_definition.md#width) of the room, in `tiles`
   - If the `room` is horizontal, the `width` must be larger than the `height`.
   - If the `room` is vertical, the `height` must be larger than the `width`.
   - The `biome` may limit the number of `tiles`.
1. Determine the amount of objects the room will contain:
   - Since every `room` must have at least one [door](../definitions/object_type_definition.md#door-objects), one slot must be reserved.
   - `Room type` and `biome` may influence the distribution of `terrain`, `items` and other objects.

The object number does not limit any game engine to add more objects to the room, it only influences how many objects the `Level Generator` will process.

Once this variables are known, the `Level Generator` can build the room.

This step can only run once per room.

#

| [Previous](levels.md) | [Next](terrain.md) |
| --------------------- | ------------------ |
