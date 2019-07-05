# Defining Methods

Let's defined the `distance` method on the `Point` struct:

```rust
#[derive(Debug)]
struct Point {
    x: usize,
    y: usize,
}

impl Point {
    fn distance(&self) -> f64 {
        ((self.x.pow(2) + self.y.pow(2)) as f64).sqrt()
    }
}

fn main() {
    let point = Point { x: 5, y: 10 };
    println!("The distance from the origin is {} units.",
             point.distance());
}
```
