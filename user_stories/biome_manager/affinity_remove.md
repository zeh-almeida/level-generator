| [Biome Affinity Set Stories](affinity_set.md) | [Biome Affinity Check Stories](affinity_check.md) |
| --------------------------------------------- | ------------------------------------------------- |

# Biome Affinity Remove Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome affinity
```

## Stories

- As a `Biome Maintainer`, I want to `remove the affinity between two Biomes` when I supply the `remove` modifier to the command with `two inputs`;

- As a `Biome Maintainer`, I want to `check the affinities of a specific Biome` when I supply the `no modifiers` and a `single input` to the command;

## Acceptance Criteria

- Given `any input` that `is empty or white space only` when `maintaining Biome affinity` and `regardless of the modifier` then the `Biome Manager` must `respond with an error`.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `two Biome names as input` with the `remove modifier` when `maintaining Biome affinity` then the `Biome Maintainer` must `remove the affinity between the two Biomes`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

- Given `no Biome name matches any of the given inputs exactly` when `maintaining Biome affinity` then the `Biome Manager` must `respond with an error`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-008` with the message `Biome was not found` and the `input supplied`.

- Given a `single input` with `no modifiers` when `maintaining Biome affinity` then the `Biome Manager` must `find the Biome` and `display its affinities`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the `exactly matching name` then the `Biome Manager` must `respond with an error`.
  The `error` must contain the code `BE-008` with the message `Biome was not found`.

  Only one model can be matched.

## Contracts

#

| [Biome Affinity Set Stories](affinity_set.md) | [Biome Affinity Check Stories](affinity_check.md) |
| --------------------------------------------- | ------------------------------------------------- |
