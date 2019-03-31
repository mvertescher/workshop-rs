# The Standard Library

- The _foundation_ of portable Rust software
- `std` is available to all crates by default
- Parts of `std` can be brought into scope via `use`:
  - ex. `use std::env;`

### A Quick Tour
  - Options and errors: `Option<T>` and `Result<T, E>`
  - Iterators: `std::iter` and the `Iterator` trait
  - Contiguous memory regions:
    - `Vec<T>`: A heap-allocated _vector_ that is resizable at runtime.
    - `[T; n]`: An inline _array_ with a fixed size at compile time.
    - `[T]`: A dynamically sized slice into any other kind of contiguous storage, whether heap-allocated or not.
  - Slices
    - `&[T]`: _shared slice_
    - `&mut [T]`: _mutable slice_
    - `Box<T>`: _owned slice_
  - UTF-8 strings: `&str` and `String`
  - Utilities for printing `String`s: `std::fmt` and associated macros
  - Data sharing: `Rc`, `Cell`, `RefCell`, `Arc` and `Mutex`
  - `std::collections`: maps, sets, linked lists and others.
  - Platform abstractions and I/O
    - Typically I/O: `io`, `fs` and `net`
    - Threading: `thread`, `sync`, `atomic`, `mpsc`
