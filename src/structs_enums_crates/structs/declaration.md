# Declaration

Declarations are a little different between C and Rust:

```c
typedef struct {
    char *name;
    char *path;
    size_t entries;
    bool is_busy;
} sContext;
```

```rust
struct Context {
    name: String,
    path: String,
    entries: usize,
    is_busy: bool,
}
```
