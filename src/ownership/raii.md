# RAII

RAII stands for: _Resource Acquisition is Initialization_.

When a `String` goes out of scope, a `drop` function is called.

```rust,ignore
{
  let s = String::from("hello"); // s is valid
  // do stuff with s
} // Scope is over, `s` is no longer valid, `drop` is called
```

Informally, ownership is lexically scoped.
