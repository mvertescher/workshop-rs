# Ownership can be Tedious!

For a clearer example of where ownership is tedious, consider this:

```rust
fn main() {
 let s1 = String::from("hello");
 let (s2, len) = calculate_length(s1);
 println!("The length of '{}' is {}.", s2, len);
}

fn calculate_length(s: String) -> (String, usize) {
  let length = s.len(); // len() returns the length of a String
  (s, length)
}
```

We don't need to take ownership to `calculate_length`!
