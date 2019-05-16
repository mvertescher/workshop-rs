# Numeric Casting

In specific situations, we can cast between integer types.

For example, we can cast an `i32` to an `i64`:

```rust
let x: i32 = 5;

let y = x as i64;
```

We can also do these casts:

```rust
let one = true as u8;
let at_sign = 64 as char;
let two_hundred = -56i8 as u8;
```
