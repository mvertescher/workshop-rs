# Return Values

Functions can also return value. The return type is written to the right of
`->`.

```rust,editable
fn main() {
    let x = pow_2(5);

    println!("The value of x is: {}", x);
}

fn pow_2(x: u32) -> u32 {
    x * x
}
```
