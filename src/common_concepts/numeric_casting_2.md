# Numeric Casting

It's important to be careful when casting integer types:

```rust
fn main() {
  let x: u64 = 0x1_0000_0002;
  let y = x as u32;
  assert_eq!(2, y);
}
```

In this case, a truncation occurs and the `assert_eq` is valid.
