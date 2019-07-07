# Methods With More Parameters

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

    fn is_further_than(&self, other: &Point) -> bool {
        self.distance() > origin.distance()
    }
}

fn main() {
    let point = Point { x: 5, y: 10 };
    let other = Point { x: 10, y: 10 };
    println!("Is {:?} further from the origin than {:?}... {}",
             point, other, point.is_further_than(&other));
}
```

Note that `self` is never passed in by the caller.
