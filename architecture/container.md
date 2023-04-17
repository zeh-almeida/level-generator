| [System Context](system.md) | [Component: Biome Manager](component_biome.md) |
| --------------------------- | ---------------------------------------------- |

# Container

![Container](diagrams/imgs/container.png)

## Level Generator

The `Level Generator` is a `software system` and therefore can be defined as the interaction between different `containers`.

### Biome Manager Container

`Container` responsible for managing all [Biome](../requirements/definitions/biome_definition.md) data in the system.

It is detailed [here](component_biome.md).

### Object Manager Container

`Container` responsible for managing all [Object](../requirements/definitions/object_definition.md) data in the system.

It is detailed [here](component_object.md).

### Generator Executor Container

`Container` responsible for generating the `Level` according to the [especification](../requirements/generation/levels.md).

It is detailed [here](component_executor.md).

### Data Communication Layer Container

Abstracts the communication with the `Data Repository`.

This allows the other `containers` have less knowledge about the uderlying data storage, making them simpler and easier to use.

Errors must be validated and if unrecoverable, must throw specific `exceptions` to the caller.

This `container` cannot be executed directly by any `user`.

### Data Repository Container

Stores and manages data for the `Level Generator`.

It should handle the [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) paradigm for the models.

#

| [System Context](system.md) | [Component: Biome Manager](component_biome.md) |
| --------------------------- | ---------------------------------------------- |
