# Answer 2

We manually implement the `Display` trait for types since it is used for
user-facing output:

```rust
use std::fmt;

struct City {
    name: String,
    state: String,
}

impl fmt::Display for City {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "{}, {}", self.name, self.state)
    }
}

fn main() {
    let x = City { name: String::from("Boston"), state: String::from("MA") };
    println!("{}", x);
}
```
