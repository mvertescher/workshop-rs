# Matching `Result`

To extract `T`, in this case `File`, from `Result`, we can use a match statement:

```rust,should_panic
use std::fs::File;

fn main() {
    let f = File::open("emojis.json");

    let _f = match f {
        Ok(file) => file,
        Err(error) => {
            panic!("There was a problem opening the file: {:?}", error)
        },
    };
}
```

On success, we return the concrete `File` type. Otherwise, we panic.
