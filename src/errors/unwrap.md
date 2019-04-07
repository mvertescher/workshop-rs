# Shortcuts for `panic!`: `unwrap`

Previously, we've used match to `panic!` on error:

```rust,should_panic
use std::fs::File;

fn main() {
    let f = File::open("emojis.json");

    let _f = match f {
        Ok(file) => file,
        Err(_) => panic!(),
    };
}
````

We seen this before! In more detail, `unwrap` is a method of `Result` (also
available with `Option`) that can help here:

```rust,should_panic
use std::fs::File;

fn main() {
    let _f = File::open("emojis.json").unwrap();
}
```

`unwrap` is shorthand for "give me `T` or `panic!`".

This is most useful in early prototyping situations.
