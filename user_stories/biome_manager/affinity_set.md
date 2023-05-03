| [Biome Removal Stories](removal.md) | [Biome Affinity Remove Stories](affinity_remove.md) |
| ----------------------------------- | --------------------------------------------------- |

# Biome Affinity Set Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome affinity set
```

## Stories

- As a `Biome Maintainer`, I want to `set the affinity level of two Biomes` when I supply `their exact names`;

## Acceptance Criteria

- Given `any input` that `is empty or white space only` when `setting Biome affinity` then the `Biome Manager` must `respond with an error`.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `two Biome names as input` when `setting Biome affinity` then the `Biome Maintainer` must `supply the affinity level`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `affinity level` must be `positive`, `negative` or `neutral` exclusively.

  If no `affinity level` is supplied, it is assumed as `neutral`.

  If an `affinity level` already exists between the two `Biomes` it must be `overwritten`.

  If the `affinity level supplied` is not `positive`, `negative` or `neutral` then the `Biome Manager` must `respond with an error`. The `error` must contain the code `BE-009` with the message `Affinity must be positive, negative or neutral`.

  Once the `affinity level` is set, `Biome Maintainer` must `respond with a success message`. The `success message` must contain the code `BS-003` with the message `<BIOME1> - <BIOME2> affinity <AFFINITY>` where `<BIOME1>` is the `first input` value, `<BIOME2>` is the `second input` and `<AFFINITY>` is the `affinity level`.

- Given `at least one of the inputs does not match an existing Biome` when `setting Biome affinity` then the `Biome Manager` must `respond with an error`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-008` with the message `Biome was not found` and the `unmatched input`.

## Contracts

### Default affinity

Input:

```
test1 test2
```

Output:

```
BS-003: test1 - test2 affinity neutral
```

### Supplied affinity

Input:

```
test1 test2 positive
```

Output:

```
BS-003: test1 - test2 affinity positive
```

### Empty input

Input:

```

```

Output:

```
BE-006: Biome name must be given
```

### Missing input

Input:

```
test1
```

Output:

```
BE-006: Biome name must be given
```

### Mismatched input

Input:

```
test1 test9
```

Output:

```
BE-008: Biome was not found test9
```

### Bad affinity

Input:

```
test1 test2 test
```

Output:

```
BE-009: Affinity must be positive, negative or neutral
```

#

| [Biome Removal Stories](removal.md) | [Biome Affinity Remove Stories](affinity_remove.md) |
| ----------------------------------- | --------------------------------------------------- |
