# Question 3

Let's take another look at `serde`!

## [`serde`](serde) Deserializer Lifetimes

```rust
#[derive(Deserialize)]
struct User<'a> {
    id: u32,
    name: &'a str,
    screen_name: &'a str,
    location: &'a str,
}
```

> User struct above, that borrows string or byte array data from the string or
> byte array holding the input. This avoids allocating memory to store a string
> for each individual field and then copying string data out of the input over
> to the newly allocated field. Rust guarantees that the input data outlives
> the period during which the output data structure is in scope, meaning it is
> impossible to have dangling pointer errors as a result of losing the input
> data while the output data structure still refers to it.

Specifically, the `Deserialize<'de>` lifetime records the constraints on how
long data borrowed by this type must be valid.

Let's look at an example of this:

```rust,ignore
use serde_derive; // 1.0.90
use serde_json; // 1.0.39

use serde_derive::Deserialize;

#[derive(Debug, Deserialize)]
struct User<'a> {
    id: u32,
    name: &'a str,
    screen_name: &'a str,
    location: &'a str,
}

fn get_user() -> User {
    let data = r#"
        {
            "id": 1,
            "name": "Ted Plummer",
            "screen_name": "Arthur",
            "location": "The Ocean"
        }"#;
    serde_json::from_str(data).unwrap()
}

fn main() {
    println!("{:?}", get_user());
}
```

Is this a compiler error? [Playpen][playpen]

[playpen]: https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=08e1e0d2c910d2b5dd2554328386137f
[serde]: https://serde.rs/lifetimes.html
