# The Standard Library

- The _foundation_ of portable Rust software
- `std` is available to all crates by default
- Parts of `std` can be brought into scope via `use`:
  - ex. `use std::env;`

In recent times, the standard library consists of two parts:

- `core`: A _minimal_ platform dependency free (no heap, no I/O, no concurrency) foundation.
- `std`: `core` plus `platform depenpendent core types.

`core` is a subset of `std`.

We'll circle back on this when we talk about crates without the `std` library!
