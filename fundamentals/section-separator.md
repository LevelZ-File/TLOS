# Section Separator

**Authors**:

- Gregory Mitchell, 2024

## Synopsis

All LevelZ data sections are separated by three dashes `---`. "Three Dashes" is defined as three consecutive characters of the `U+002D` unicode, named "Hyphen-Minus." This is defined as the "Section Separator" and should be referred to as such in all official material, including documentation.

No other characters or data is allowed before or after the Section Separator, including any whitespace characters.

At least one Section Separator is required in a `.lvlz` file, which is defined to separate between the [Data Section](/fundamentals/data-section/) and the [Level Section](/fundamentals/level-section/).

## Correct Usage

```lvlz
---
```

## Incorrect Usage

```lvlz
 ---
```

```lvlz
--- abc
```

```lvlz
--
```
