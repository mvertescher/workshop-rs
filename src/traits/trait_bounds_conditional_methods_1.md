# Using Trait Bounds to Conditionally Implement Methods

We can use a trait bound in an `impl` block to conditionally implement methods
for types that implement specific traits.

For example, we can implement `cmp_display` for `Pair<T>` if `T` is `Display`
and `PartialOrd`.

```rust
use std::fmt::Display;

struct Pair<T> {
    x: T,
    y: T,
}

impl<T> Pair<T> {
    fn new(x: T, y: T) -> Self {
        Self {
            x,
            y,
        }
    }
}

impl<T: Display + PartialOrd> Pair<T> {
    fn cmp_display(&self) {
        if self.x >= self.y {
            println!("The largest member is x = {}", self.x);
        } else {
            println!("The largest member is y = {}", self.y);
        }
    }
}
```
