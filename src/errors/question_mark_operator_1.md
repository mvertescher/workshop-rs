# The `?` Operator

There are a few more things to note about `?`:

`?` can only be used with the `Result` type because of the way it is defined.

Can we use the `?` in our main function?

```rust,editable
use std::fs::File;

fn main() {
    // Uncomment below!
    // let _f = File::open("emojis.json")?;
}
```
