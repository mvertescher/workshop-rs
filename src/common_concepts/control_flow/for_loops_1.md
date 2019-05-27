# `for` Loops

We can adjust our countdown code slightly to use a `for` loop:

```rust
fn main() {
    let a = [5, 4, 3, 2, 1];

    for number in a.iter() {
        println!("{} ", number);
    }

    println!("LIFTOFF!!!");
}
```
