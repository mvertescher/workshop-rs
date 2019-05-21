# Arrays

Arrays in Rust are fixed in length and every value in an array has the same
type.

We can declare an array of values of the same type:

```rust
let a = [1, 2, 3, 4, 5];
```

Also, we can declare an array with a _type annotation_:

```rust
let a: [u8; 5] = [1, 2, 3, 4, 5];
```

We can access elements:

```rust
let a = [1, 2, 3, 4, 5];
let first = a[0];
```
