# Question 2

Given a new type, how do we [`Display`][display] it?

```rust,editable
struct City {
    name: String,
    state: String,
}

fn main() {
/*
    let x = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{}", x);
*/
}
```

[display]: https://doc.rust-lang.org/std/fmt/trait.Display.html
