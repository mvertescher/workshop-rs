# Generic Structs

When declaring structs with generic parameters, we must declare them after the
struct name inside angled brackets:

```rust
struct Point<T> {
    x: T,
    y: T,
}

fn main() {
    let integer = Point { x: 5, y: 10 };
    let float = Point { x: 1.0, y: 4.0 };
}
```

`Point<T>` holds `x` and `y` values both of type `T`.
