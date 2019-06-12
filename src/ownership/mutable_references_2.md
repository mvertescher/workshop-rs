# Mutable References

Let's fix our example by using `mut`:

```rust
fn main() {
  let mut s = String::from("hello");
  change(&mut s);
}

fn change(some_string: &mut String) {
  some_string.push_str(", world");
}
```
