# Tile Characteristics

[Tiles](../definitions/tile_definition.md#what-is-a-tile) must be given their size before anything else.
This ensures all steps are aware of the tile constant, helping them decide on objects and placements.

## Constraints

The `Level Generator` must validate the [tile size](../definitions/tile_definition.md#tile-size) and store its value for later use.

This value must be provided from the environment. If not supplied, assume the default value.