# Ownership and Structs

Can structs store references?

```rust
struct Context {
    name: &str,
    path: &str,
    entries: usize,
    is_busy: bool,
}

let context = Context {
    name: "Context",
    path: "/home/context",
    entries: 0,
    is_busy: false,
};
```
