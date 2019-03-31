# Reading Elements

There are two ways to reference a value stored in a vector: indexing syntax or
the `get` method.

```rust
let v = vec![1, 2, 3, 4, 5];

let third: &i32 = &v[2];
println!("The third element is {}", third);

match v.get(2) {
    Some(third) => println!("The third element is {}", third),
    None => println!("There is no third element."),
}
```

We can match on the [`get`
method](https://doc.rust-lang.org/std/vec/struct.Vec.html?search=#method.get)
above because it returns `Option<T>`.
