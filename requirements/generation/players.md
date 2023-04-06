| [Previous](npcs.md) |
| ------------------- |

# Player Characters Placement

## Description

[Player Characters](../definitions/object_type_definition.md#pc-objects) do not respect the final number of `objects` in the `room` because it is used as a generation guide, not a generated object.

It is the responsability of the engine to render the `PC` in the `room`, not the `Level Generator`.

At the same time, the `PC` is useful in order to determine the placement of other objects, like `doors` and `terrain`.

`PC` must be able to trasverse a `room` without limitations. This means they should be able to reach every `door` or `corridor` in a `room`.

## Examples

Examples for those interactions are available:

- [PC and Doors/Corridors](doors.md#examples)
- [PC and Terrain](terrain.md#examples)

#

| [Previous](npcs.md) |
| ------------------- |
