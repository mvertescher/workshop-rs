# Setting up `criterion.rs`

We should add `criterion` as a dependency when _running tests only_.

```toml
[dev-dependencies]
criterion = "0.2"

[[bench]]
name = "is_prime"
harness = false
```

The `[bench]` section defines one benchmark test `is_prime` that uses a custom
test harness.
