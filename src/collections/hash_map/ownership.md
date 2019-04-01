# Ownership

The `insert` method _moves_ data into the hash map.

```rust
use std::collections::HashMap;

let field_name = String::from("Favorite color");
let field_value = String::from("Blue");

let mut map = HashMap::new();
map.insert(field_name, field_value);
// `field_name` and `field_value` are now invalid!

println!("{:?}", map);
```

The map above now owns `field_name` and `field_value`.
