| [User Stories](../README.md) | [Biome Selection Stories](selection.md) |
| ---------------------------- | --------------------------------------- |

# Biome Creation Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md).

- As a `Biome Maintainer`, I want to `Create Biomes` in order to have them available for `Level Generation`;

- As a `Biome Maintainer`, I want to `know when my Biome has an invalid name` in order to make sure the `model is valid`;

- As a `Biome Maintainer`, I want to `create multiple Biomes at the same time`;

## Acceptance Criteria

- Given a `Biome name` that `is longer than 50 characters` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  The `error` must contain the code `BE-001` with the message `Biome name must be 50 characters or less`.

- Given a `Biome name` that `is empty` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  The `error` must contain the code `BE-002` with the message `Biome name is empty`.

- Given a `Biome name` that `is only white spaces` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  The `error` must contain the code `BE-003` with the message `Biome name is empty`.

- Given a `Biome name with non-alphanumeric characters` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  The `error` must contain the code `BE-004` with the message `Biome name must be alphanumeric`.

- Given a `Biome name with alphanumeric characters and between 1 and 50 characters in length` when `creating the Biome` then the `Biome Manager` must check `if the Biome already exists`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  If `another Biome with the same name ignoring case exists` the `Biome Manager` must raise an `error` with code `BE-005` with the message `Biome already exists: '<NAME>'` where `<NAME>` is the `input` value.

- Given a `Biome name with alphanumeric characters and between 1 and 50 characters in length` when `creating the Biome` and `no Biome exists with the same name` then the `Biome Manager` must `respond with a success message`.

  The `input` must be trimmed of all `white spaces` at the beggining and the end before validation.

  The `success message` must contain the code `BS-001` with the message `Biome created: '<NAME>'` where `<NAME>` is the `input` value.

- Given multiple `Biome name inputs` when `creating multiple Biomes` then the `Biome Manager` must `validate each and every entry`.

  At the end, the `Biome Manager` must list which `inputs` were successful and which `inputs` failed, together with their respective `error messages`.

  Each entry must be separated by `a new line`, according to the environment: `Windows = CR/LF`, `*nix = LF`.

  Each entry must be trimmed of all `white spaces` at the beggining and the end before validation.

  An `empty line` is considered the `end of the input`.

#

| [User Stories](../README.md) | [Biome Selection Stories](selection.md) |
| ---------------------------- | --------------------------------------- |
