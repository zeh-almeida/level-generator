| [Biome Creation Stories](creation.md) | [User Stories](../README.md) |
| ------------------------------------- | ---------------------------- |

# Biome Selection Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

## Stories

- As a `Biome Maintainer`, I want to `list all existing Biomes`;

- As a `Biome Maintainer`, I want to `search Biomes by exact name`;

## Acceptance Criteria

- Given a `Biome name` that `is longer than 50 characters` when `selecting a Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-001` with the message `Biome name must be 50 characters or less`.

- Given a `Biome name` that `is empty or white space only` when `selecting a Biome` then the `Biome Manager` must `perform a full selection`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

- Given a `full selection` when `selecting a Biome` then the `Biome Manager` must `order Biome names alphabetically`.

- Given a `selected Biome` when `selecting one Biome` then the `Biome Manager` must `show the Biome name and affinities`.

- Given a `selected Biome` when `selecting all Biomes` then the `Biome Manager` must `show the Biome names only`.

- Given a `Biome name with alphanumeric characters and between 1 and 50 characters in length` when `selecting Biomes` then the `Biome Manager` must `search for an exact match`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the desired name, nothing should be returned.

  Only one model can be returned.

- Given a `Biome name regex` when `selecting Biomes` then the `Biome Manager` must `search for partial matches`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the desired name, nothing should be returned.

  One or more models can be returned.

#

| [Biome Creation Stories](creation.md) | [User Stories](../README.md) |
| ------------------------------------- | ---------------------------- |
