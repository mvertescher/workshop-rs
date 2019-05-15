# Type Annotations

Sometimes types cannot be inferred.

In that case, we must _annotate_ types.

For example, we can annotate floats:

```rust
let x = 6.4;      // f64 by default

let x: f32 = 3.2; // f32 annotated
```

Typically, we should always rely on type inference unless we _must_ annotate
types.
