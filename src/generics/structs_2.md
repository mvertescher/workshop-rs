# Generic Structs

What happens if we create a point with `x` and `y` as different types?

```rust,ignore
struct Point<T> {
    x: T,
    y: T,
}

fn main() {
    let wont_work = Point { x: 5, y: 4.0 };
}
```

```plaintext
error[E0308]: mismatched types
 --> src/main.rs:7:38
  |
7 |     let wont_work = Point { x: 5, y: 4.0 };
  |                                      ^^^ expected integer, found floating-point number
  |
  = note: expected type `{integer}`
             found type `{float}`
```

Remember that a `T` must be a single known type at compile time.
