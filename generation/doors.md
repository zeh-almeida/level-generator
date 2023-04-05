| [Previous](terrain.md) | [Next](items.md) |
| ---------------------- | ---------------- |

# Door/Corridor Placements

## Description

[Doors and corridors](../definitions/object_definition.md#door-objects) are placed in a [room](../definitions/room_definition.md#what-is-a-room) in order to connect it to a neighboring `room`.

Each and every `door` must be accessible by the [PC objects](../definitions/object_definition.md#pc-objects).

In order to do so, the `door/corridor` must be placed on a `tile` that has an adjacent free `tiles` the same `height` of the object next to it and their reference `tile` must be always connected to a surface of the `room`.

This means a `door/corridor` can be placed on the ceiling, floor or walls of any `room` as long as there is space available.

This space must be reachable by a [PC Object](../definitions/object_type_definition.md#pc-objects) from any part of the `room`: it cannot have any `terrain` or other `tile` obstruction in its path.

`Doors` and `corridors` must respect the final number of objects in the `room`. At the same time, `rooms` are required to have at least one `door` or `corridor`.

### Example 1

Given a `door` that has `height = 2` and `length = 1`, place it at the leftmost corner of the `room`;

Given that the `PC Object` has a `height = 2` and `length = 1`;

In order to have this `door` accessible, a two tile-high, one tile-long empty space must exist at the right of this `door`, the same size and length of the `PC Object`.

At the same time, the `room` that connects using this `door` must have a two tile-high, one tile-long empty space at the left of this `door`.

### Example 2

Given a `corridor` that has `height = 2` and `length = 1`, place it at the rightmost corner of the `room`;

Given that the [PC Object](../definitions/object_type_definition.md#pc-objects) has a `height = 2` and `length = 1`;

In order to have this `corridor` accessible, a two tile-high, one tile-long empty space must exist at the right of this `corridor`, the same size and length of the `PC Object`.

At the same time, the `room` that connects using this `corridor` must have a two tile-high, one tile-long empty space at the right of this `corridor`.

### Example 3

Given a `door` that has `height = 1` and `length = 2`, place it at the leftmost corner of the `room`;

Given that the `PC Object` has a `height = 2` and `length = 1`;

This `door` becomes unaccesible by the `PC Object` and must be removed from the `room`.

In order to have it accessible, it should be placed either on the `floor` or `ceiling` of this `room`.

| [Previous](terrain.md) | [Next](items.md) |
| ---------------------- | ---------------- |
