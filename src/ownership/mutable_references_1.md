# Mutable References

What happens when we try to mutate a reference?

```rust,compile_fail
fn main() {
  let s = String::from("hello");
  change(&s);
}

fn change(some_string: &String) {
  some_string.push_str(", world");
}
```
