# Ways Variable and Data Interact: Move

To recap, a _move_:

- Performs a shallow copy
- Invalidates the original variable
- Transfers ownership of the value to the new variable

By default, Rust will never make 'deep' copies.

_Automatic_ is assumed to be cheap in Rust!
