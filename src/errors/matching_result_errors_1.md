# Matching `Result` Errors

What if we want to handle some errors differently?

Since the type of `E` is a struct `io::Error` that has a `kind` method that
returns an `io::ErrorKind` enum, we can add another `match` statement:

```rust,no_run
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let f = File::open("emojis.json");

    let _f = match f {
        Ok(file) => file,
        Err(error) => match error.kind() {
            ErrorKind::NotFound => match File::create("emojis.json") {
                Ok(fc) => fc,
                Err(e) => panic!("Tried to create file but there was a problem: {:?}", e),
            },
            other_error => panic!("There was a problem opening the file: {:?}", other_error),
        },
    };
}
```

If the file is not found, we can handle the error and create it.
