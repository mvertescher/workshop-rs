# A Heap Allocated `String`

Heap memory must be requested from the OS.

We need a way to return back the memory to the OS when done.

```rust,ignore
// `::from` calls `malloc()`
let mut s = String::from("hello");
```

... but we need to call `free()`!
