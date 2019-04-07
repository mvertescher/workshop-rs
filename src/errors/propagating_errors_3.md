# Propagating Errors

In fact, we can chain `?` operators together:

```rust
use std::io;
use std::io::Read;
use std::fs::File;

fn read_username_from_file() -> Result<String, io::Error> {
    let mut s = String::new();

    File::open("emojis.json")?.read_to_string(&mut s)?;

    Ok(s)
}
```

Furthermore, reading a file to a `String` is so common, there's a function for
it `fs::read_to_string`:

```rust
use std::io;
use std::fs;

fn read_username_from_file() -> Result<String, io::Error> {
    fs::read_to_string("emojis.json")
}
```
