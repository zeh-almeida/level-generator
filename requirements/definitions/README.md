| [Requirements](../README.md) |
| ---------------------------- |

# Definitions

## Introduction

In order to understand the `level Generator` process, one must be familiar with the different models used during the execution.

Each model is dedicated to explain a function or behavior for the execution. This includes how they interact with each other, attributes, properties and limitations.

## Models

- [Tiles](tile_definition.md#what-is-a-tile) - Every model is based on tiles
- [Level](level_definition.md#what-is-a-level) - The result of the generation process
- [Biome](biome_definition.md#what-is-a-biome) - Enables a level of diversity in `rooms` and `levels`
- [Room](room_definition.md#what-is-a-room) - Tile-based space where `objects` interact with eh `biome`
- [Object](object_definition.md#what-is-an-object) - Elements capable of changing how environments interact during the generation.

## Basic Data Types

Throughout the definitions, there will be mentions of values such as `integers`, `bits` and such.

This section tries to explain in a simpler way what those values mean.

### 1-bit Value

A `1-bit` value is the definition of binary: it is either `1` or `0`.

It is normally used as a status flag or condition.

### 4-bit Integer

An `4-bit integer` is a `4-bit` value which is represented in memory as: `0000`.

`Unsigned` numbers are capable of storing values from `0` up to `15`.

`Signed` numbers lose one `bit` in order to store the sign: `positive` or `negative`. Because of this limitation, they capable of storing values from `-7` up to `7`.

### 8-bit Integer

An `8-bit integer` is a `8-bit` value which is represented in memory as: `00000000`.

`Unsigned` numbers are capable of storing values from `0` up to `255`.

`Signed` numbers lose one `bit` in order to store the sign: `positive` or `negative`. Because of this limitation, they capable of storing values from `-127` up to `127`.

### 16-bit Integer

An `16-bit integer` is a `16-bit` value which is represented in memory as: `0000000000000000`.

`Unsigned` numbers are capable of storing values from `0` up to `65535`.

`Signed` numbers lose one `bit` in order to store the sign: `positive` or `negative`. Because of this limitation, they capable of storing values from `-32767` up to `32767`.

### Strings

A `string` is an array of characters. Most of the time, characters are represented by an `unsigned 8-bit integer` value but that changes depending on the [encoding](#string-encoding) used.

#### Example:

`a` is a character but `test` is a `string`, because the characters are together in a single representation.

### String Encoding

[Wikipedia has a very good explanation on the subject](https://en.wikipedia.org/wiki/Character_encoding).

When considering the `Level Generator`, all `characters` should use the `UTF-8` encoding exclusively.

#

| [Requirements](../README.md) |
| ---------------------------- |
