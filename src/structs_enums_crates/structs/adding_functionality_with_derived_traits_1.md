# Adding Functionality with Derived Traits

Often, we would like to display the contents of our structures:

```rust,compile_fail
struct Point {
    x: usize,
    y: usize,
}

fn main() {
    let point = Point { x: 3, y: 10 };
    println!("{}", point);
}
```
