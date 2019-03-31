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

Another way of creating `HashMap`s is by `collect`ing a vector of tuples.

`zip`ing two vectors creates a single vector of tuples.

```rust
use std::collections::HashMap;

let teams  = vec![String::from("Blue"), String::from("Yellow")];
let initial_scores = vec![10, 50];

let scores: HashMap<_, _> = teams.iter().zip(initial_scores.iter()).collect();

println!("{:?}", scores);
```

`HashMap<_, _>` is require with `collect` because we could collect other data
structures.

However, we can use `_` for `K` and `V` since these can be inferred.
