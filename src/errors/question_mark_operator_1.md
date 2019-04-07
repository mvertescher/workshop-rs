# The `?` Operator

There are a few more things to note about `?`:

`?` can only be used with the `Result` type because of the way it is defined.

Can we use the `?` in our main function?

```rust
use std::fs::File;

fn main() {
    let _f = File::open("emojis.json")?;
}
```
