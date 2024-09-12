# Scroll Header

**Authors**:

- Gregory Mitchell, 2024

## Synopsis

The `@scroll` header outlines the auto-scrolling direction inside of a 2D level. Thus, this standard only applies to levels that specify their `@type` to be `2`. As a result, this header is not standardized and can be used for other purposes in non-2D levels. However, the `@scroll` header is **optional** inside of a 2D `.lvlz` file.

The name must be in lowercase and spelled as shown. Bindings should not be allowed to parse alternative names for the `@scroll` header unless it serves a different purpose. A "different purpose" is defined to be a separate definition that is reasonably different from the definition of a `@scroll` header, being that it defines the auto-scrolling direction inside of a 2D level.

The value of the `@spawn` header must be one of five values:

- `none`, meaning no auto-scrolling is implemented
- `horizontal-left`, meaning the direction is moving *from the right to the left*
- `horizontal-right`, meaning the direction is moving *from the left to the right*
- `vertical-down`, meaning the direction is moving *from the top to the bottom*
- `vertical-up`, meaning the direction is moving *from the bottom to the top*

The interpretation of the `@scroll` header is up to user and binding implementation. As a result of being optional, bindings may deviate from `none` if the `@scroll` header is not provided, while official bindings should recognize `none` as its default value. If provided, users should specify the `@scroll` header immediately after the `@spawn` header, defining it as the third header in the file.

Information regarding speed, angle, and/or other related parameters are up to alternative headers from binding implementation. For example, bindings may allow unofficial parameters regarding two or more scrolling directions at specific locations, with this one serving as the first. However, these may not interfere with the standard outlined above, being a singular direction.

## Correct Usage

```lvlz
@type 2
@spawn default
@scroll horizontal-right
```

```lvlz
@type 2
@spawn [0, 100]
@scroll vertical-down
```

## Incorrect Usage

**Reason**: `@scroll` is not allowed in 3D levels (error)

```lvlz
@type 3
@spawn [0, 10, 0]
@scroll vertical-down
```

**Reason**: `@scroll` must be defined after the `@type` header (error)

```lvlz
@scroll none
@type 2
@spawn default
```

**Reason**: `@scroll` should be defined after the `@spawn` header (warning)

```lvlz
@type 2
@scroll none
@spawn default
```
