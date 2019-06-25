# Constructor Short Hand

To reduce verbosity, Rust has a shorthand for constructing structs:

```rust,ignore
fn new(name: String, path: String) -> Context
    Context {
        name: name,
        path: path,
        entries: 0,
        is_busy: false,
    }
}
```

Above is the same as:

```rust,ignore
fn new(name: String, path: String) -> Context
    Context {
        name,
        path,
        entries: 0,
        is_busy: false,
    }
}
```
