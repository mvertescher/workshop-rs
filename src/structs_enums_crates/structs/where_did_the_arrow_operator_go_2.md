# Where did `->` go?

Rust has a feature called _automatic referencing and dereferencing_:

```rust,ignore
impl Point {
    fn distance(&self) -> f64 {
        ((self.x.pow(2) + self.y.pow(2)) as f64).sqrt()
    }
}

// The following are the same
point.distance();
(&point).distance();
```

The `&`, `&mut` or `*` are added by the compiler to match the signature of the
method.
