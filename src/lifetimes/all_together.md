# Generics, Trait Bounds, and Lifetimes Together

Let's tie everything together with this example:

```rust
use std::fmt::Display;

fn longest_with_an_announcement<'a, T>(x: &'a str, y: &'a str, ann: T) -> &'a str
    where T: Display
{
    println!("Announcement! {}", ann);
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

We're finding and returning the longest `&str` and printing a type that can be
`Display`ed to stdout.
