# Other Slices

There are other types of slices as well.

Here is a `&[i32]` slice:

```rust
let a: [i32; 5] = [1, 2, 3, 4, 5];

let slice = &a[1..3];
```
