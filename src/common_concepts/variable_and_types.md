# Variables and Types

When declared, variables are assigned a type.

```rust
fn main() {
    let mut s = "This is a `&str` type";
    s = s.len();
}
```

You cannot assign mismatch types when assigning variables.

```plaintext
$ cargo run
   Compiling test-rs v0.1.0 (/home/mv/dev/test-rs)
error[E0308]: mismatched types
 --> src/main.rs:3:9
  |
3 |     s = s.len();
  |         ^^^^^^^ expected &str, found usize
  |
  = note: expected type `&str`
    found type `usize`
```
