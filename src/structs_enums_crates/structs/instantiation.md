# Instantiation

We can create a new struct like so:

```c
sContext context = {
    .name = "Context",
    .path = NULL,
    .entries = 0,
    .is_busy = false,
};
```

```rust
let context = Context {
    name: String::from("Context"),
    path: String::from("/home/context"),  // NULL not possible!
    entries: 0,
    is_busy: false,
};
```

Note: the internal representation of these structures are not the same even
though they are roughly functionally equivalent.
