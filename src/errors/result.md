# `Result`

In C, there are a variety of different recoverable error handling techniques:
- None: Ignore errors with `void` returns
- Binary: `bool` or `int` 0 on success failure otherwise
- Status code: `int` 0 or a status code integer
- Overloaded status code: 0 on success, status code if less than 0, meaningful
  unsigned integer return if greater than zero
- Robust: Error are pointers to structures (heap allocated) with associated
  debugging data
- Or even a combination of above!

In Rust, there is a [`core` (ubiquitous) type](https://doc.rust-lang.org/core/result/) for functions that can fail:

```rust
enum Result<T, E> {
    Ok(T),
    Err(E),
}
```

We say: `Result<T, E>` is an enum with two variants `Ok` and `Err`. Both `T`
and `E` are _generic type parameters_ (like `Option<T>`).

`T` represents the type that will be returned in the success case and `E`
represents the error type that will returned in the failure case.
