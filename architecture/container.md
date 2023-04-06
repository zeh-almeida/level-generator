| [System Context](system.md) |
| --------------------------- |

# Container

![Container](diagrams/imgs/container.png)

## Level Generator

The `Level Generator` is a `software system` and therefore can be defined as the interaction between different `containers`.

### Biome Manager Container

Accessible via a [Command Line Interface](https://en.wikipedia.org/wiki/Command-line_interface).

Enables [CRUD operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) for [biome](../requirements/definitions/biome_definition.md) data.

Should perform all validations according to the `especifications`.

Errors should be returned to the `User` using `stderr`.

### Object Manager Container

Accessible via a [Command Line Interface](https://en.wikipedia.org/wiki/Command-line_interface).

Enables [CRUD operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) for [object](../requirements/definitions/object_definition.md) data.

Should perform all validations according to the [especifications](../requirements/generation/rooms.md).

Errors should be returned to the `User` using `stderr`.

### Generator Executor Container

Accessible via a [Command Line Interface](https://en.wikipedia.org/wiki/Command-line_interface).

Must perform the execution according to the [especification](../requirements/generation/README.md), making sure to respect the ordering, validations and due process of the generation.

Errors should be returned to the `User` using `stderr`.

| [System Context](system.md) |
| --------------------------- |
