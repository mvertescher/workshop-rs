# Question 1

Given a new type, how do we `Debug` print it?

```rust,editable
struct City {
    name: String,
    state: String,
}

/*
fn main() {
    let x = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{:?}", x);
}
*/
```