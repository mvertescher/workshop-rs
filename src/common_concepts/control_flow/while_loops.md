# `while` Loops

`while` loops also work similarly to C.

Let's write a countdown:

```rust
fn main() {
    let a = [5, 4, 3, 2, 1];
    let mut index = 0;

    while index < 5 {
        println!("{} ", a[index]);

        index += 1;
    }

    println!("LIFTOFF!!!");
}
```
