# Question 1

Given a new type, `City`, how do we [`Debug`][debug] print it?

```rust,editable
struct City {
    name: String,
    state: String,
}

fn main() {
/*
    let x = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{:?}", x);
*/
}
```

[debug]: https://doc.rust-lang.org/std/fmt/trait.Debug.html
