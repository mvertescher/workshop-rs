# Propagating Errors

Over time, it was discovered that propagating errors up was _so common_ that
Rust provides the `?` operator to make this easier.

Here's the last example simplified:

```rust
use std::io;
use std::io::Read;
use std::fs::File;

fn read_username_from_file() -> Result<String, io::Error> {
    let mut f = File::open("emojis.json")?;
    let mut s = String::new();
    f.read_to_string(&mut s)?;
    Ok(s)
}
```

`?` works almost identically to the `match` statements we had previously. It
produces `T` on success or early returns `E`.

The difference between the two is that `?` uses the `from` function, defined in
the [`From` trait][from_trait], to convert errors when returning `E`.

[from_trait]: https://doc.rust-lang.org/std/convert/trait.From.html
