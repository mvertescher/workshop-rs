# Adding Functionality with Derived Traits

Ouch, let's try the `:?` formatter instead:

```rust,does_not_compile
struct Point {
    x: usize,
    y: usize,
}

fn main() {
    let point = Point { x: 3, y: 10 };
    println!("{:?}", point);
}
```
