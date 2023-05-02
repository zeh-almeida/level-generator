| [Biome Single Selection Stories](selection_single.md) | [Biome Affinity Stories](affinity.md) |
| ----------------------------------------------------- | ------------------------------------- |

# Biome Removal Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome remove
```

## Stories

- As a `Biome Maintainer`, I want to `remove a single Biome and all its affinity data`;

## Acceptance Criteria

- Given a `input` that `is empty or white space only` when `removing a Biome` then the `Biome Manager` must `respond with an error`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  The `error` must contain the code `BE-006` with the message `Biome name must be given`.

- Given `multiple matching biomes` when `selecting single Biomes` then the `Biome Manager` must `respond with an error`.

  The `response` must list all `biomes matching the input`.

  The `error` must contain the code `BE-007` with the message `multiple biomes match the criteria`.

- Given a `input with alphanumeric characters only` and `with at least one character in length` when `removing a Biome` then the `Biome Manager` must `be used as a regular expression`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the desired name then the `Biome Manager` must `respond with an error`.
  The `error` must contain the code `BE-008` with the message `Biome was not found`.

  Only one model can be matched.

- Given a `Regular Expression` when `selecting single Biomes` then the `Biome Manager` must `search for partial matches`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If the `Regular Expression` is not valid, then the `Biome Manager` must `respond with an error`.
  The `error` must contain the code `BE-005` with the message `Biome name expression is invalid`.

  If no `Biome` is found with the `matching name` then the `Biome Manager` must `respond with an error`.
  The `error` must contain the code `BE-008` with the message `Biome was not found`.

  If a `Biome` is found with the matching `input` then the `Biome Manager` must `show the full list of affinities of this Biome` and then `remove it`. `Biome Manager` should also output a message with code `BS-002` and content `Biome removed successfully`.

  Only one model can be matched.

## Contracts

### Empty input

Input:

```

```

Output:

```
BE-006: with the message Biome name must be given
```

### Multiple matches

Input:

```
test*
```

Output:

```
test1
test2
test3
test4
test5
BE-007: multiple biomes match the criteria
```

### No matches found

Input:

```
test6
```

Output:

```
BE-008: Biome was not found
```

### Invalid expression

Input:

```
,[
```

Output:

```
BE-005: Biome name expression is invalid
```

### Valid input

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

BS-002: Biome removed successfully
```

#

| [Biome Single Selection Stories](selection_single.md) | [Biome Affinity Stories](affinity.md) |
| ----------------------------------------------------- | ------------------------------------- |
