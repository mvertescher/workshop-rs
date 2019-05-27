# `for` Loops

Finally, we can use a range to iterate over:

```rust
fn main() {
    for number in (1..6).rev() {
        println!("{} ", number);
    }

    println!("LIFTOFF!!!");
}
```
