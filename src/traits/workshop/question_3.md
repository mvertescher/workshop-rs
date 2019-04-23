# Question 3

How do we [`Debug`][debug] and [`Display`][display] the `City` type now?

```rust,editable
enum Country {
    Canada,
    Mexico,
    UnitedStates,
}

struct City {
    name: String,
    state: String,
    country: Country,
}

fn main() {
/*
    let city = City {
        name: String::from("Boston"),
        state: String::from("MA"),
        country: Country::UnitedStates,
    };

    println!("Debug:   {:?}", city);
    println!("Display: {}", city);
*/
}
```

[debug]: https://doc.rust-lang.org/std/fmt/trait.Debug.html
[display]: https://doc.rust-lang.org/std/fmt/trait.Display.html
