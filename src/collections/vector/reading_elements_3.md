# Reading Elements

What happens when we reference a vector element and then try to modify the
vector?

```rust,ignore,does_not_compile
let mut v = vec![1, 2, 3, 4, 5];

let first = &v[0];

v.push(6);

println!("The first element is: {}", first);
```

```text
error[E0502]: cannot borrow `v` as mutable because it is also borrowed as immutable
  --> src/main.rs:11:1
   |
5  | let first = &v[0];
   |              - immutable borrow occurs here
6  |
7  | v.push(6);
   | ^ mutable borrow occurs here
...
10 | }
   | - immutable borrow ends here
```
