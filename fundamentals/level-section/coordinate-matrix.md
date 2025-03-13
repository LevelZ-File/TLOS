# Block

**Authors**:

- Gregory Mitchell, 2025

## Synopsis

A "Coordinate Matrix" specifies a rectangular space in a Level Section. The bounds portion must be separated between parenthesis `()` and then must immediately be bound to a center coordinate using the `^` character. Each Matrix specifies a minimum and maximum coordinate based on its dimensions. The center coordinate is used to calculate where the Matrix is placed in the Level Section.

Coordinate Matrix dimensions must be equal to the `@type` header specified in the data section. If the value of `@type` is `2`, 2D coordinates must be used. If the value of `@type` is `3`, 3D coordinates must be used. Parsers should refuse to parse incorrect coordinates.

A Coordinate Matrix can be appended to other coordinates or other coordinate matrixes using the appending character (`*`). This allows for multiple coordinates and coordinate matrices to be placed on the same line.

## Correct Usage

```lvlz
@type 2
---
block: (0, 5, 0, 5)^[2, 2]
```

```lvlz
@type 3
---
block: (0, 5, 0, 5, 0, 5)^[2, 2, 2]
```

```lvlz
@type 2
---
block: (-1, 3, 2, 4)^[-2, 2]*(2, 5, 3, 6)^[-4, -2]*[0, 0]
```

## Incorrect Usage

**Reason**: Center must be bound to the bounds using the `^` character.

```lvlz
@type 2
---
block: (0, 5, 0, 5) [2, 2]
```

**Reason**: Bounds must be separated by a comma.

```lvlz
@type 2
---
block: (0 5 0 5)^[2, 2]
```

**Reason**: Center must be separated by a comma.

```lvlz
@type 2
---
block: (0, 5, 0, 5)^[2 2]
```

**Reason**: Coordinate Matrix does not match dimension specified in the `@type` header.

```lvlz
@type 2
---
block: (0, 5, 0, 5, 0, 5)^[2, 2]
```
