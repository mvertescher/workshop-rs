# Update Syntax

Rust also has a shorthand for updating structures:

```rust,ignore
let context1 = Context {
    name: String::from("Context"),
    path: String::from("/home/context"),
    entries: 0,
    is_busy: false,
};
```

Above is the same as:

```rust,ignore
let context2 = Context {
    entries: 1,
    ..context1 // `Context1` moved
};
```
