# Vector Basics

`Vec` from `std::vec::Vec` is included in the prelude.

We can create a new `Vec` explicitly:

```rust
let v: Vec<i32> = Vec::new();

println!("{:?}", v);
```

Or we can create a new `Vec` with some initial content via a macro `vec!`:

```rust
let v = vec![1, 2, 3];

println!("{:?}", v);
```

We can create the same `Vec` using the `push` method:

```rust
let mut v = Vec::new();

v.push(1);
v.push(2);
v.push(3);

println!("{:?}", v);
```

When a vector goes out of scope, all its contents are dropped.
