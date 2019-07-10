# Question 2

Refactor the code below by creating a new function called `mutate_hello` that
mutates the `String` hello and returns the newly mutated `String`.

```rust,editable
fn main() {
    let mut hello = String::from("hello");
    let mutate = |s: &mut String| s.truncate(4);
    mutate(&mut hello);
    println!("{}", hello);
}
```
