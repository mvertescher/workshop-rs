# Ownership and Functions

How does ownership relate to functions?

```rust
fn main() {
  let s = String::from("hello");
  takes_ownership(s);

  let x = 5;
  makes_copy(x);
}

fn takes_ownership(s: String) {
  println!("{}", s);
} // String `s` is `drop`ed here

fn makes_copy(x: u32) {
  println!("{}", x);
} // Nothing happens to `x` here, it was on the stack
```
