# What is a Tile

Tile is the fundamental unit for the `Level Generator`.

Everything is made of tiles:

- Rooms are an arrengement of tiles in specific order;
- NPCs and PCs occupy a number of tiles;
- Every object is contained in one or more tiles;
- etc.

Tiles are always square: they have the same width and height.
These values are absolute for the generation, meaning there can never be a tile with a different size in a `Level Generator` execution.

Of course, the tile size can be different in a new execution of the `Level Generator`.
