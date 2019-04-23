# Answer 3

[`Debug`][debug] can be conditionally derived if subtypes are [`Debug`][debug].

When manually implemented [`Display`][display], we have options.

```rust,editable
use std::fmt;

#[derive(Debug)]
enum Country {
    Canada,
    Mexico,
    UnitedStates,
}

#[derive(Debug)]
struct City {
    name: String,
    state: String,
    country: Country,
}

impl fmt::Display for City {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "{}, {}, {:?}", self.name, self.state, self.country)
    }
}

fn main() {
    let city = City {
        name: String::from("Boston"),
        state: String::from("MA"),
        country: Country::UnitedStates,
    };

    println!("Debug:   {:?}", city);
    println!("Display: {}", city);
}
```

[debug]: https://doc.rust-lang.org/std/fmt/trait.Debug.html
[display]: https://doc.rust-lang.org/std/fmt/trait.Display.html
