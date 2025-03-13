# Block List

**Authors**:

- Gregory Mitchell, 2025

## Synopsis

A "Block List" is a list of Blocks that are randomized in a LevelZ File. Blocks are listed in between curly braces (`{}`) and separated with a comma (`,`). This allows for a random selection of Blocks to be placed in a Level. A different Block is chosen for each raw coordinate in the Level Section.

A Block List can optionally specify the percentage change of each block to be placed at the specified coordinates. Percentages are declared in a double format and must add up to `1` (100%). If no percentages are specified, each block is given an equal chance of being placed.

## Correct Usage

```lvlz
{magma, water, stone}: [0, 0]*[0, 1]*[0, 2]
```

```lvlz
{0.5=magma, 0.25=water, 0.25=stone}: [0, 0]*[0, 1]*[0, 2]
```

## Incorrect Usage

**Reason**: Brackets were not properly closed.

```lvlz
{magma, water, stone: [0, 0]*[0, 1]*[0, 2]
```

**Reason**: Block List must be on the same line with its Coordinates.

```lvlz
{magma, water, stone}
[0, 0]*[0, 1]*[0, 2]
```

**Reason**: Block List is not separated by a colon.

```lvlz
{magma, water, stone} [0, 0]*[0, 1]*[0, 2]
```

**Reason**: Percentages do not add up to `1`.

```lvlz
{0.25=magma, 0.25=water, 0.25=stone}: [0, 0]*[0, 1]*[0, 2]
```
