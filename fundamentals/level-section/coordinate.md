# Header

**Authors**:

- Gregory Mitchell, 2025

## Synopsis

A "Coordinate" is a list of two or three integers that represent a point in a two-dimensional or three-dimensional space. Coordinates are used to define the position of a "Block" in a "Level Section."

Coordinates must be specified after a "Block" in the "Level Section" and must be separated by a colon character (`:`). Parsers should not allow any other character to separate a "Block" from "Coordinates."

A coordinates' dimension must match the dimension specified in the `@type` header according to the LevelZ Standard. If the value of `@type` is `2`, 2D coordinates must be used. If the value of `@type` is `3`, 3D coordinates must be used. Parsers should refuse to parse incorrect coordinates.

Coordinates can be appended to one another using the `*` character. This allows for multiple coordinates to be placed on the same line. They can also be spread across a rectangular space using a "Coordinate Matrix."

## Correct Usage

```lvlz
@type 2
---
block: [0, 0]
```

```lvlz
@type 3
---
block: [0, 0, 0]*[0, 0, 1]
```

## Incorrect Usage

**Reason**: Coordinates must be on the same line with its Block.

```lvlz
block
[0, 0]
```

**Reason**: Coordinates are not separated by a colon.

```lvlz
block [0, 0]
```

**Reason**: Coordinates do not match the dimension specified in the `@type` header.

```lvlz
@type 2
---
block: [0, 0, 0]
```

**Reason**: Coordinates were not appended properly.

```lvlz
block: [0, 0][0, 1]
```
