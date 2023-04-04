| [Previous](rooms.md) | [Next](doors.md) |
| -------------------- | ---------------- |

# Terrain Object Selection

## Description

[Terrain objects](../definitions/object_definition.md#terrain-objects) are trickier to select.
They must consider the [biome](../definitions/biome_definition.md#what-is-a-biome) and [room type](../definitions/room_definition.md#what-is-a-room-type) because there may be limitations to what objects can be placed.

### Limitation scenario

In a `volcano` biome you shouldn't place `tree` objects.

## Details

At this point, the `Level Generator` is already aware of:

- `Room type` allows for terrain objects or not
- `Biome` restricts terrain objects or not
- The `room` is vertical or horizontal

However, in order to place a `terrain object` the `Level Generator` must also take into consideration:

- What is the size of the `terrain object`, does it respect the `room` borders?
- Will the `terrain object` leave enough space for a `door`?
- Will the `terrain object` leave enough space horizontally or vertically to cross the object in the `room`?

Those questions allow the `Level Generator` to select an object with a matching criteria.

It is also possible that no object matches this criteria, so no object will be selected.

This step can be skipped or executed as many times as the `room` has reserved slots for terrain objects.

### Example 1

If a `slope` terrain object leans on the bottom left corner of the `room`, a `door` placed there will not be accessible, so this `door` should be moved to the right of the `slope`.

### Example 2

The `room` has a `width = 6` and `height = 6`.

If a `slope` terrain object of `width = 3` and `height = 6` is selected, the `doors` should be placed to the left and/or the top of the `room`.

### Example 3

The `room` has a `width = 6` and `height = 6`.

If a `slope` terrain object of `width = 7` and `height = 2` is selected, it cannot fit the `room` and must be discarded.

The same would happen if the object had `width = 2` and `height = 7`, for example.

### Example 4

The `room` has a `width = 6` and `height = 6`.

If a `square` terrain object of `width = 5` and `height = 5` is selected, it can only be used if at least one `door` object allows for a `height = 1`.

| [Previous](rooms.md) | [Next](doors.md) |
| -------------------- | ---------------- |
