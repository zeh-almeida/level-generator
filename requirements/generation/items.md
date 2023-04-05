| [Previous](doors.md) | [Next](npcs.md) |
| -------------------- | --------------- |

# Item Placement

## Description

[Items](../definitions/object_definition.md#items-objects) can be placed on any `tile` of the `room`, including [terrain objects](../definitions/object_definition.md#terrain-objects).

Their orientation depends on their definition. This means `items` can be placed on the `ceiling` for example, if their definition and their anchor point allows.

`Items` must respect the size of the `room` when being placed. This means they must fit within the bounds of the `room` and must not go through `terrain objects`, `doors` or `corridors`.

`Items` should not interfere with the ability of a [PC Object](../definitions/object_type_definition.md#pc-objects) to trasverse the `room`: they are only placed in the `room` to help with `level setup` after the generation is complete.

`Items` must respect the final number of objects in the `room`. This however does not stop the user of the end-result of the `Level Generator` to add more `items` after the process is complete.

| [Previous](doors.md) | [Next](npcs.md) |
| -------------------- | --------------- |
