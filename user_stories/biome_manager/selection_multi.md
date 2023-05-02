| [Biome Creation Stories](creation.md) | [Biome Single Selection Stories](selection_single.md) |
| ------------------------------------- | ----------------------------------------------------- |

# Biome Multi Selection Stories

Stories must follow the [requirements](../../requirements/definitions/biome_definition.md) and [architecture](../../architecture/README.md).

The execution of the following stories expect the execution of the `CLI` command:

```
biome select
```

## Stories

- As a `Biome Maintainer`, I want to `list all existing Biomes`;

- As a `Biome Maintainer`, I want to `search Biomes by a Regular Expression`;

## Acceptance Criteria

- Given a `input` that `is empty or white space only` when `selecting a Biome` then the `Biome Manager` must `perform a full selection`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

- Given `multiple results` when `selecting a Biome` then the `Biome Manager` must `order Biome names alphabetically`.

- Given `multiple results` when `selecting all Biomes` then the `Biome Manager` must `show the Biome names only`.

- Given a `input with alphanumeric characters only` and `with at least one character in length` when `selecting Biomes` then the `Biome Manager` must `be used as a regular expression`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If no `Biome` is found with the desired name, nothing should be returned.

- Given a `Regular Expression` when `selecting Biomes` then the `Biome Manager` must `search for partial matches`.

  The `input` must be trimmed of all `white spaces` at the beginning and the end before validation.

  If the `Regular Expression` is not valid, then the `Biome Manager` must `respond with an error`. The `error` must contain the code `BE-005` with the message `Biome name expression is invalid`.

  If no `Biome` is found with the desired name, nothing should be returned.

  One or more models can be returned.

## Contracts

### Alphanumeric only

Input:

```
test
```

Output:

```
test
```

### Match found

Input:

```
test*
```

Output:

```
test
test1
test2
test3
test4
test5
```

### Match not found

Input:

```
*test0*
```

Output:

```

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

#

| [Biome Creation Stories](creation.md) | [Biome Single Selection Stories](selection_single.md) |
| ------------------------------------- | ----------------------------------------------------- |
