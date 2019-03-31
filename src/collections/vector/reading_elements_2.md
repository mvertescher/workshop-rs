# Reading Elements

Indexing into a non-existent element results in a panic:

```rust
let v = vec![1, 2, 3, 4, 5];

let does_not_exist = &v[100];
```

Calling `get()` on a non-existent element returns `None`:

```rust
let v = vec![1, 2, 3, 4, 5];

let does_not_exist = v.get(100);

# assert_eq!(None, does_not_exist);
```
