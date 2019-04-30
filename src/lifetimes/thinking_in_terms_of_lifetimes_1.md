# Thinking in Terms of Lifetimes

The way you need to specify lifetime parameters depends on what your function
is doing.

If the `longest` function always returned the first parameter, we would omit
the lifetime on the second parameter:

```rust
fn longest<'a>(x: &'a str, y: &str) -> &'a str {
    x
}
```

The second parameter `y` does not influence `x` or the return value in any way.
We only relate the lifetime of `x`, `'a`, to the output parameter.
