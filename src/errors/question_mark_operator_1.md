# The `?` Operator

There are a few more things to note about `?`:

`?` can be used with types other than `Result` if they implement the trait
[std::ops::Try][try], like `Option`.

Can we use the `?` in our main function?

```rust,editable
use std::fs::File;

fn main() {
    // Uncomment below!
    // let _f = File::open("emojis.json")?;
}
```

[try]: https://doc.rust-lang.org/std/ops/trait.Try.html
