# Adding Functionality with Derived Traits

Ouch, let's try the `:?` formatter instead:

```rust,compile_fail
struct Point {
    x: usize,
    y: usize,
}

fn main() {
    let point = Point { x: 3, y: 10 };
    println!("{:?}", point);
}
```
