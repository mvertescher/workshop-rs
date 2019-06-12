# Mutable References

But, what happens when we try to change the same `String` twice?

```rust,compile_fail
fn main() {
  let mut s = String::from("hello");
  let mut s1 = &mut s;
  let mut s2 = &mut s;
  change(&mut s1);
  change(&mut s2);
}

fn change(some_string: &mut String) {
  some_string.push_str(", world");
}
```
