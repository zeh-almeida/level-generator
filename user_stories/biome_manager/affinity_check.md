| [Biome Affinity Remove Stories](affinity_remove.md) | [User Stories](../README.md) |
| --------------------------------------------------- | ---------------------------- |

# Biome Affinity Check Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome affinity
```

## Stories

- As a `Biome Maintainer`, I want to `check the affinities of a specific Biome`;

## Acceptance Criteria

- Given a `single input` that `is empty or white space only` when `checking Biome affinity` then the `Biome Manager` must `respond with an error`.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given a `single Biome name as input` when `checking Biome affinity` then the `Biome Maintainer` must `list all explicit affities of this Biome`.

  `The input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  Only one model can be matched.

- Given `the single input does not match an existing Biome` when `checking Biome affinity` then the `Biome Manager` must `respond with an error`.

  `The input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-008` with the message `Biome was not found` and the `unmatched input`.

## Contracts

### Empty input

Input:

```

```

Output:

```
BE-006: Biome name must be given
```

### Mismatched input

Input:

```
test9
```

Output:

```
BE-008: Biome was not found
```

### Regular execution

Input:

```
test
```

Output:

```
Biome: test

Link  Affinity
----  --------
test1 Positive
test2 Negative
test3 Negative
test4 Positive
test5 Positive
```

#

| [Biome Affinity Remove Stories](affinity_remove.md) | [User Stories](../README.md) |
| --------------------------------------------------- | ---------------------------- |
