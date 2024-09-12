# Header

**Authors**:

- Gregory Mitchell, 2024

## Synopsis

The "Data Section" contains "Headers" that serve as metadata for a `.lvlz` file. They communicate parameters necessary for the correct understanding of a file.

Headers will include a "name" and a "value" at the beginning of each line. A Header will take up one line of space, which includes its "name" and "value." The "name" and "value" must be separated by one space character, defined as the unicode `U+0020` and most popularily typed by the biggest key on your keyboard.

The "name" of a header must follow a `lower_snake_case` format and cannot include spaces. Names must be prefixed by an `@` symbol, defined as the unicode `U+0040` and named the "Commercial At" symbol. On QWERTY keyboards, it is typed when pressing `Shift` and `2` at the same time. There are no restrictions for characters inside the name of a header.

The "value" of a header does not follow any specific standard and can contain anything relevant, as long as the above and below standards are met.

### Standardized Headers

A "standardized" header is a header name and value that are **officially** recognized as a core part of the file format language. Names and values must follow a specific format outlined in this file.

Standardized headers are located in the [headers](/fundamentals/data-section/headers/) folder.

## Correct Usage

```lvlz
@name value
@longer_name second value
@+_plus 23
@20 three
```

## Incorrect Usage

**Reason**: Invalid header line (error)

```lvlz
@name
value
```

**Reason**: Headers should be properly named (warning)

```lvlz
@LongerName value
```
