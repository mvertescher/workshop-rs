# Lifetime Annotations in Struct Definitions

It's possible for structs to hold references.

We need to add a lifetime parameter to every reference in the definition.

```rust
struct ImportantExcerpt<'a> {
    part: &'a str,
}

fn main() {
    let novel = String::from("Call me Ishmael. Some years ago...");
    let first_sentence = novel.split('.')
        .next()
        .expect("Could not find a '.'");
    let i = ImportantExcerpt { part: first_sentence };
}
```

The lifetime of `part` must outlive the lifetime of `ImportantExcerpt`!
