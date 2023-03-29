| [Previous](rooms.md) | [Next](doors.md) |
| -------------------- | ---------------- |

# Terrain Object Selection

[Terrain objects](../definitions/object_definition.md#terrain-objects) are trickier to select.
They must consider the [biome](../definitions/biome_definition.md#what-is-a-biome) and [room type](../definitions/room_definition.md#what-is-a-room-type) because there may be limitations to what objects can be placed.

For example:
In a `volcano` biome you shouldn't place `tree` objects.

The `Level Generator` must be made aware of:

- Does the room type allows for terrain objects?
- Does the biome restricts terrain objects?
- Is the room vertical or horizontal?
- Where are the current connections to the room?
- How does the terrain piece interact with other pieces?

Those questions allow the `Level Generator` to select a object which matches what was already selected.

For example:
If a `slope` terrain object leans on the bottom left corner of the room, a door placed there is not accessible, so it should be moved to the end of the `slope`.

This step can be skipped or executed as many times as the room has reserved slots for terrain objects.

| [Previous](rooms.md) | [Next](doors.md) |
| -------------------- | ---------------- |
