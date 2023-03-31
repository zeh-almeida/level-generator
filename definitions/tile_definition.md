| [Definitions](README.md) |
| ------------------------ |

# What is a Tile

`Tile` is the fundamental unit for the `Level Generator`.

Everything is made of `tiles`:

- [Rooms](room_definition.md#rooms) are an arrengement of tiles in specific order;
- Every [object](object_definition.md#objects) is contained in one or more `tiles`;
- etc.

`Tiles` are always square: they have the same width and height.
These values are absolute for the generation, meaning there can never be a tile with a different size in a `Level Generator` execution.

Of course, the `tile size` can vary in a new execution of the `Level Generator`.

## Properties

### Tile Size

The `tile size` must be the same across a `Level Generator` execution in order to keep rooms and object consistent.

The size must be represented as a `unsigned 8-bit integer` and must be greater than zero. If no value is specified, should use the value of `4`.

| [Definitions](README.md) |
| ------------------------ |
