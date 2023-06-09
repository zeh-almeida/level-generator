| [User Stories](../README.md) | [Biome Single Selection Stories](selection_single.md) |
| ---------------------------- | ----------------------------------------------------- |

# Biome Creation Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome create
```

## Stories

- As a `Biome Maintainer`, I want to `Create Biomes` in order to have them available for `Level Generation`;

- As a `Biome Maintainer`, I want to `know when my Biome has an invalid name` in order to make sure the `model is valid`;

- As a `Biome Maintainer`, I want to `create multiple Biomes at the same time`;

## Acceptance Criteria

- Given a `Biome name` that `is longer than 50 characters` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-001` with the message `Biome name must be 50 characters or less`.

- Given a `Biome name` that `is empty` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-002` with the message `Biome name is empty`.

- Given a `Biome name` that `is only white spaces` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-002` with the message `Biome name is empty`.

- Given a `Biome name with non-alphanumeric characters` when `creating the Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-003` with the message `Biome name must be alphanumeric`.

- Given a `Biome name with alphanumeric characters and between 1 and 50 characters in length` when `creating the Biome` then the `Biome Manager` must check `if the Biome already exists`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If `another Biome with the same name ignoring case exists` the `Biome Manager` must raise an `error` with code `BE-004` with the message `Biome already exists: '<NAME>'` where `<NAME>` is the `input` value.

- Given a `Biome name with alphanumeric characters and between 1 and 50 characters in length` when `creating the Biome` and `no Biome exists with the same name` then the `Biome Manager` must `persist the model` and `respond with a success message`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `success message` must contain the code `BS-001` with the message `Biome created: '<NAME>'` where `<NAME>` is the `input` value.

- Given multiple `Biome name inputs` when `creating multiple Biomes` then the `Biome Manager` must `validate each and every entry`.

  At the end, the `Biome Manager` must list which `inputs` were successful and which `inputs` failed, together with their respective `error messages`.

  Each entry must be separated by `a blank space`.

  Each entry must be trimmed of all `white spaces` at the beginning and the end before validation.

  An `empty line` is considered the `end of the input`.

## Contracts

### Single Item

#### Success path

Input:

```
test
```

Output:

```
BS-001 | Biome created: 'test'
```

#### Error path 1

Input:

```
abcdefghijklmnopqrstuwxyz0123456789ABCDEFGHIJKLMNO
```

Output:

```
BE-001 | Biome name must be 50 characters or less
```

#### Error path 2

Input:

```

```

Output:

```
BE-002 | Biome name is empty
```

#### Error path 3

Input:

```
test!
```

Output:

```
BE-003 | Biome name must be alphanumeric
```

#### Error path 4

Input:

```
test test
```

Output:

```
BS-001 | Biome created: 'test'
BE-004 | Biome already exists: 'test'
```

### Multiple Items

Input:

```
multi1 multi2 multi3
```

Output:

```
BS-001 | Biome created: 'multi1'
BS-001 | Biome created: 'multi2'
BS-001 | Biome created: 'multi3'
```

#

| [User Stories](../README.md) | [Biome Single Selection Stories](selection_single.md) |
| ---------------------------- | ----------------------------------------------------- |
