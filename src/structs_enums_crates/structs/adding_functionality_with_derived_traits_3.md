# Adding Functionality with Derived Traits

Let's 'derive' the `Debug` trait:

```rust
#[derive(Debug)]
struct Point {
    x: usize,
    y: usize,
}

fn main() {
    let point = Point { x: 3, y: 10 };
    println!("{:?}", point);
}
```
