# The `?` Operator

We can specify a `Result` return in our main function to use the `?` operator:

```rust
use std::error::Error;
use std::fs::File;

fn main() -> Result<(), Box<dyn Error>> {
    let _f = File::open("emojis.json")?;

    Ok(())
}
```

`Box<dyn Error>` is something called a _trait object_. For now, this means any
kind of error. More on this later!
