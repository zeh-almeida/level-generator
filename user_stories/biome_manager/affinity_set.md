| [Biome Removal Stories](removal.md) | [Biome Affinity Remove Stories](affinity_remove.md) |
| ----------------------------------- | --------------------------------------------------- |

# Biome Affinity Set Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome affinity set
```

## Stories

- As a `Biome Maintainer`, I want to `set the affinity level of two Biomes` with `their exact names`;

## Acceptance Criteria

- Given `any input` that `is empty or white space only` when `maintaining Biome affinity` and `regardless of the modifier` then the `Biome Manager` must `respond with an error`.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `two Biome names as input` when `setting Biome affinity` then the `Biome Maintainer` must `supply the affinity level`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `affinity level` must be `positive`, `negative` or `neutral` exclusively.

  If no `affinity level` is supplied, it is assumed as `neutral`.

- Given `one of the inputs does not have a Biome match` when `setting Biome affinity` then the `Biome Manager` must `respond with an error`.

  `Any input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-008` with the message `Biome was not found` and the `input supplied`.

## Contracts

#

| [Biome Removal Stories](removal.md) | [Biome Affinity Remove Stories](affinity_remove.md) |
| ----------------------------------- | --------------------------------------------------- |
