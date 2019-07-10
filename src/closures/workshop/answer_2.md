# Answer 2

```rust,editable
fn main() {
    let hello = mutate_hello(|s| {
        s.truncate(4);
    });
    println!("{}", hello);
}

fn mutate_hello<F: Fn(&mut String) -> ()>(f: F) -> String {
    let mut hello = String::from("hello");
    f(&mut hello);
    hello
}
```
