# Answer 1

Although uncommon, we can manually implement the [`Debug`][debug] trait:

```rust
use std::fmt;

struct City {
    name: String,
    state: String,
}

impl fmt::Debug for City {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "City {{ name: {:?}, state: {:?} }}", self.name, self.state)
    }
}

fn main() {
    let c = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{:?}", c);
}
```

Normally, we use an _annotation_ to derive the [`Debug`][debug] trait:

```rust
#[derive(Debug)]
struct City {
    name: String,
    state: String,
}

fn main() {
    let c = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{:?}", c);
}
```

[debug]: https://doc.rust-lang.org/std/fmt/trait.Debug.html
