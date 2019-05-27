# `if` in a `let` Statement

Does this compile correctly?

```rust,compile_fail
fn main() {
    let condition = true;
    let number = if condition {
        5
    } else {
        "Six"
    };
    println!("The value of number is: {}", number);
}
```
