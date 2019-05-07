# Setting up `criterion.rs`

We should also create an `is_prime` benchmark file in the `benches` directory.

In `benches/is_prime.rs`:

```rust,ignore
#[macro_use]
extern crate criterion;

use criterion::Criterion;
use criterion::black_box;

use primes_workshop;

fn my_is_prime_benchmark(c: &mut Criterion) {
    c.bench_function("primes_workshop::is_prime 999983", |b| b.iter(||
        primes_workshop::is_prime(black_box(999983))
    ));
}

criterion_group!(benches, my_is_prime_benchmark);
criterion_main!(benches);
```
