# Adding Meaning with Structs

There are often many ways a representing data:

```rust
let x = 3;
let y = 10;
```

```rust
let point = (3, 10);
```

Structs enabled us to be more descriptive about field contents.

```rust
struct Point {
  x: usize,
  y: usize,
}

fn main() {
  let _point = Point { x: 3, y: 10 };
}
```
