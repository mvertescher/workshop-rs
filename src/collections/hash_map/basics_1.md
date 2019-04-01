# Hash Map Basics

Like vectors, hash map data is stored on the heap.

Unlike vectors, `HashMap` is not included in the prelude and must be brought
into scope.

```rust
use std::collections::HashMap;

let mut scores = HashMap::new();

scores.insert(String::from("Blue"), 10);
scores.insert(String::from("Yellow"), 50);

println!("{:?}", scores);
```
