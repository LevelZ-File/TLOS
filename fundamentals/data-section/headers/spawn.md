# Spawn Header

**Authors**:

- Gregory Mitchell, 2024

## Synopsis

The `@spawn` header outlines the spawnpoint of a level. This is often used to determine where a level should start, where a character is placed, and more. However, the interpretation of the `@spawn` header's purpose for developers is not and will not standardized. Therefore, it is reasonable for usage of the header to be located at any starting position.

The name must be in lowercase and spelled as shown. Bindings should not be allowed to parse alternative names for the `@spawn` header unless it serves a different purpose. A "different purpose" is defined to be a separate definition that is reasonably different from the definition of a `@spawn` header, being that it defines the starting point of a LevelZ File.

The value of the `@spawn` header must be a proper coordinate according to the dimension in the `@type` header previously. In addition to this, the value of the header can be a literal `"default"` string to define the default implementation of the parser. Therefore, the `@spawn` header is both required and must be placed after the `@type` header.

## Correct Usage

```lvlz
@type 2
@spawn [0, 0]
```

```lvlz
@type 3
@spawn [1, 2, 3]
```

```lvlz
@type 2
@spawn default
```

## Incorrect Usage

**Reason**: `@spawn` header must be before `@type` header (error)

```lvlz
@spawn default
@type 2
```

**Reason**:

Depending on interpretation, one of two are possible:

- `@spawn` header must be present (error)
- Headers should be properly named (warning)

```lvlz
@Spawn [-2, 2]
@type 2
```
