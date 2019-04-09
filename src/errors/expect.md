# Shortcuts for `panic!`: `expect`

We've also seen `panic!` on error with a message:

```rust,should_panic
use std::fs::File;

fn main() {
    let f = File::open("emojis.json");

    let _f = match f {
        Ok(file) => file,
        Err(error) => panic!("There was a problem opening the file: {:?}", error),
    };
}
````

The `expect` method of `Result` (also available with `Option`) that can help here:

```rust,should_panic
use std::fs::File;

fn main() {
    let _f = File::open("emojis.json").expect("Failed to open emojis.json");
}
```

`expect` is shorthand for "give me `T` or `panic!` with a message".

This is useful in situations when we would like more information about where a
panic is in the code.
