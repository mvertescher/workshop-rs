# Storing Closures using Generic Parameters

One technique for mitigating the runtime affects of expensive functions is to
use memory to store results. In otherwords, use a cache.

We can have a struct hold the result as well as the closure by using a `Fn`
generic trait bound:

```rust
struct Cacher<T>
    where T: Fn(u32) -> u32
{
    calculation: T,
    value: Option<u32>,
}
```

The `Cacher` struct holds a closure `T` that has one `u32` argument and a
return value of `u32`.
