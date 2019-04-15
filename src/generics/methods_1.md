# Generic Methods

We can implement methods on structs and enums using generic types:

```rust
struct Point<T> {
    x: T,
    y: T,
}

impl<T> Point<T> {
    fn x(&self) -> &T {
        &self.x
    }
}

fn main() {
    let p = Point { x: 5, y: 10 };

    println!("p.x = {}", p.x());
}
```

Note that we have to declare `T` right after `impl` so we can use it to specify
that we're implementing methods on the type `Point<T>`.

By declaring `T` as generic type after `impl`, the compiler can identify that
the type in the angle brackets in `Point` is a generic type rather than a
concrete type.
