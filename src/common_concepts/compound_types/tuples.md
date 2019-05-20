# Tuples

Tuples can contain mixed types and cannot grow or shrink.

We can created fixed tuples:

```rust
let tuple: (i8, f32, u16) = (1, 1.5, 2);
```

We can _deconstruct_ tuples:

```rust
let tuple: (i8, f32, u16) = (1, 1.5, 2);
let (a, b, c) = tuple;
```

We can _copy_ out elements:

```rust
let tuple: (i8, f32, u16) = (1, 1.5, 2);
let signed8 = tuple.0;
let float32 = tuple.1;
let unsigned16 = tuple.2;
```
