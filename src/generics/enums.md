# Generic Enums

We've seen two generic enums already:

```rust
enum Option<T> {
    Some(T),
    None,
}
```

```rust
enum Result<T, E> {
    Ok(T),
    Err(E),
}
```

For both these cases, `T` and `E` can be _any_ type.

Note that many different `Option`s or `Result`s can exist. Generics help remove
duplication.
