# Updating Values

We can use the `entry` method to fetch an element that may or may not exist.

Coupled with `or_insert`, we can add a pair if the key does not already exist:

```rust
use std::collections::HashMap;

let mut scores = HashMap::new();
scores.insert(String::from("Blue"), 10);

scores.entry(String::from("Yellow")).or_insert(50);
scores.entry(String::from("Blue")).or_insert(50);

println!("{:?}", scores)
```
