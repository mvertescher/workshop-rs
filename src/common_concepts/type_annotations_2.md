# Type Annotations

Let's consider another case where we need to parse a string as an integer.

```rust,compile_fail
fn main() {
  let number = "21".parse().expect("Not a number!");
}
```
