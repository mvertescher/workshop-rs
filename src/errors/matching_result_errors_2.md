# Matching `Result` Errors

`match`ing is quite powerful, but also primitive. `Result` provides many
methods, like [`map_err`][map_err], that accept closures instead:

```rust,no_run
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let f = File::open("emojis.json").map_err(|error| {
        if error.kind() == ErrorKind::NotFound {
            File::create("emojis.json").unwrap_or_else(|error| {
                panic!("Tried to create file but there was a problem: {:?}", error);
            })
        } else {
            panic!("There was a problem opening the file: {:?}", error);
        }
    });
}
```

The functionality above is identical to the double `match` we just saw.

[`map_err`][map_err] 'handles' the error, but leaves successful results
untouched.

This form is seen more often in the wild. We'll revisit this when we talk about
closures.

[map_err]: https://doc.rust-lang.org/std/result/enum.Result.html#method.map_err
