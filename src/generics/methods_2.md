# Generic Methods

We could implement methods only on `Point<f32>` instances rather than on
`Point<T>` instances with any generic type.

```rust
# struct Point<T> {
#     x: T,
#     y: T,
# }
impl Point<f32> {
    fn distance_from_origin(&self) -> f32 {
        (self.x.powi(2) + self.y.powi(2)).sqrt()
    }
}
```
