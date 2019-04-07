# Using `Result`

When you open a `File`, a result is returned...

```rust
use std::fs::File;

fn main() {
    let f = File::open("emojis.json");
}
```

But, what are the types `T` and `E`?

```rust,editable
use std::fs::File;

fn main() {
    // Uncomment below!
    // let f: () = File::open("emojis.json");
}
```
