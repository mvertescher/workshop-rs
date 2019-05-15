# Type Annotations

We can fix this example by adding a type annotation for the integer type we
wish to convert the string into.

```rust
fn main() {
    let number: u32 = "21".parse().expect("Not a number!");
    assert_eq!(21, number);
}
```
