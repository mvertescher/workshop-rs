# Hash Map Basics

Another way of creating `HashMap`s is by `collect`ing a vector of tuples.

`zip`ing two vectors creates a single vector of tuples.

```rust,editable
use std::collections::HashMap;

fn main() {
    let teams = vec![String::from("Blue"), String::from("Yellow")];
    let initial_scores = vec![10, 50];

    let scores: HashMap<_, _> = teams.iter().zip(initial_scores.iter()).collect();

    println!("{:?}", scores);
}
```

`HashMap<_, _>` is require with `collect` because we could collect other data
structures.

However, we can use `_` for `K` and `V` since these can be inferred.
