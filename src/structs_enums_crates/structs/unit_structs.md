# Unit Structs

A structure with no data is called a _unit struct_:

```rust
struct UnitStruct();

let unit_struct = UnitStruct();
```

This pattern is useful when we need to implement a _trait_ on a type, but have
no data to store.
