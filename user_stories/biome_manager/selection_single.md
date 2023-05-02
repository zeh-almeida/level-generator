| [Biome Multi Selection Stories](selection_multi.md) | [User Stories](../README.md) |
| --------------------------------------------------- | ---------------------------- |

# Biome Single Selection Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

## Stories

- As a `Biome Maintainer`, I want to `select a single Biome and know its data` when I `execute the selection` with the `selection modifier`;

- As a `Biome Maintainer`, I want to `search Biomes by a Regular Expression` when I `execute the selection` with the `selection modifier`;

## Acceptance Criteria

- Given the `search for a single Biome` then the `User` must provide the `-s` or `--single` modifier before the input.

- Given a `input` that `is empty or white space only` when `selecting single Biomes` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `multiple matching biomes` when `selecting single Biomes` then the `Biome Manager` must `show the first matching Biome only`.

- Given `a Biome model` when `selecting single Biomes` then the `Biome Manager` must `show the full list of affinities of the Biome`.

- Given a `input with alphanumeric characters only` and `with at least one character in length` when `selecting Biomes` then the `Biome Manager` must `be used as a regular expression`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the desired name, nothing should be returned.

  Only one model can be returned.

- Given a `Regular Expression` when `selecting single Biomes` then the `Biome Manager` must `search for partial matches`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If the `Regular Expression` is not valid, then the `Biome Manager` must `respond with an error`. The `error` must contain the code `BE-005` with the message `Biome name expression is invalid`.

  If no `Biome` is found with the desired name, nothing should be returned.

  One or more models can be returned.

## Contracts

### Alphanumeric only

Input:

```
-s test
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

### Match found

Input:

```
-s test*
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

### Match not found

Input:

```
-s *test0*
```

Output:

```

```

### Invalid expression

Input:

```
-s ,[
```

Output:

```
BE-005: Biome name expression is invalid
```

### Invalid input

Input:

```
-s
```

Output:

```
BE-006: Biome name must be given
```

#

| [Biome Multi Selection Stories](selection_multi.md) | [User Stories](../README.md) |
| --------------------------------------------------- | ---------------------------- |
