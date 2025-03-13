# Block

**Authors**:

- Gregory Mitchell, 2025

## Synopsis

Each line in the "Level Section" must start with a "Block," separated by a colon character (`:`). Parsers should not allow any other character to separate a "Block" from "Coordinates."

Blocks can be named in any file-readable format. They can optionally specify "properties" that detail extended data that differentiate Blocks with the same name.

In addition, Blocks can be randomized in a LevelZ File list by listing blocks in between curly braces (`{}`) and separating them with a comma (`,`). This is known as a "Block List."

## Correct Usage

```lvlz
block: [0, 0]
```

```lvlz
block: [0, 0]*[0, 1]
```

## Incorrect Usage

**Reason**: Block must be on the same line with its Coordinates.

```lvlz
block
[0, 0]
```

**Reason**: Block is not separated by a colon.

```lvlz
block [0, 0]
```
