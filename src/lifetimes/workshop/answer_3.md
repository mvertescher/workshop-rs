# Answer 3

We need to provide a `'static` lifetime to the `User` return of the `get_user`
function.

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

fn get_user() -> User<'static> {
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
