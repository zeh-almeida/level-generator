| [Biome Affinity Set Stories](affinity_set.md) | [Biome Affinity Check Stories](affinity_check.md) |
| --------------------------------------------- | ------------------------------------------------- |

# Biome Affinity Remove Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome affinity remove
```

## Stories

- As a `Biome Maintainer`, I want to `remove the affinity between two Biomes` when I supply `their exact names`;

## Acceptance Criteria

- Given `any input` that `is empty or white space only` when `removing Biome affinity` then the `Biome Manager` must `respond with an error`.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `two Biome names as input` when `removing Biome affinity` then the `Biome Maintainer` must `remove the affinity between the two Biomes`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If the two `Biomes` do not have any `affinity` then the `Biome Manager` must `respond with the success message`.

  Once the `affinity` is removed, `Biome Maintainer` must `respond with a success message`. The `success message` must contain the code `BS-004` with the message `<BIOME1> - <BIOME2> affinity removed` where `<BIOME1>` is the `first input` value and `<BIOME2>` is the `second input`.

- Given `at least one of the inputs does not match an existing Biome` when `removing Biome affinity` then the `Biome Manager` must `respond with an error`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-008` with the message `Biome was not found` and the `unmatched input`.

## Contracts

### Standard removal

Input:

```
test1 test2
```

Output:

```
BS-004: test1 - test2 affinity removed
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

#

| [Biome Affinity Set Stories](affinity_set.md) | [Biome Affinity Check Stories](affinity_check.md) |
| --------------------------------------------- | ------------------------------------------------- |
