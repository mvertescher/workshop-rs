# The Static Lifetime

One special lifetime is the `'static` lifetime that represents the entire
duration of the program.

```rust
let s: &'static str = "I have a static lifetime.";
```

The text of this string is stored directly into the binary of the program.

The lifetime of _all_ string literals is `'static`.

You might see the compiler suggest to you that a lifetime should be `'static`.
Often this is not the case and might be fixed a different way.
