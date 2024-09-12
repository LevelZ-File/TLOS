# Type Header

**Authors**:

- Gregory Mitchell, 2024

## Synopsis

The `@type` header determines the dimension of the LevelZ File. This is important information to determine the correct kinds of coordinates that bindings must parse. Therefore, all `.lvlz` files should start with the `@type` header.

The name must be in lowercase and spelled as shown. Bindings should not be allowed to parse alternative names for the `@type` header unless it serves a different purpose. A "different purpose" is defined to be a separate definition that is reasonably different from the definition of a `@type` header, being that it defines the dimensions of the file for its coordinates.

The value of the `@type` header is therefore either a numerical `2` or `3` character, mapped at unicodes `U+0032` and `U+0033` respectively.

## Correct Usage

```lvlz
@type 2
@other_header value
```

## Incorrect Usage

**Reason**:

Depending on interpretation, one of two are possible:

- `@type` header must be first (error)
- `@type` header must be present (error)
- Headers must be properly named (warning)

```lvlz
@Type 2
```

**Reason**: Invaild value for `@type` header (error)

```lvlz
@type 4
```

**Reason**: `@type` header must be first (error)

```lvlz
@other_header value
@type 3
```
