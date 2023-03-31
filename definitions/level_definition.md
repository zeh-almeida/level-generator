| [Definitions](README.md) |
| ------------------------ |

# Level

## What is a Level

A `level` is a collection of interconnected [rooms](room_definition.md#what-is-a-room).

`Levels` must have only two dimensions and must be finite.

All `rooms` must be reachable and traversable, even if a special condition must be met before doing so.

## Properties

The `level` must know all available [biomes](biome_definition.md) and [objects](object_definition.md) before execution, so the `rooms` can be generated with all the available data.

### Set of Biomes

The `level` must be aware of all available `biomes`, even if some of them end up not used in the generation.

This gives the possibility to better choose an option when building and validating `rooms`.

### Set of Objects

The `level` must be aware of all available `objects`, even if some of them end up not used in the generation.

This gives the possibility to better choose an option when building and validating `rooms`.

### Generated Rooms

Ordered list of all generated `rooms` so far.

The `rooms` must be ordered by their [generation number](room_definition.md#generation-number).

| [Definitions](README.md) |
| ------------------------ |
