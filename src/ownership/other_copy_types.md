# Other Copy Types

Here are a few copy types:

- All integer types: ex. `u32`
- Booleans: `bool`
- All floating point types: `f32`, `f64`
- The character type, `char`
- Tuples, if they _only_ contain types that are `copy`
- For example, `(f32, bool)` is `copy`, but `(f32, String)` is not.
