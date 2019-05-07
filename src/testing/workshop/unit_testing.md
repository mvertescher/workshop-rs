# Unit Testing `is_prime`

How might we go about adding unit tests to `is_prime`?

```rust,editable
fn first_factor(x: u64) -> u64 {
    if x % 2 == 0 {
        return 2;
    }

		// From 3 to x, stepping by 2, check if n is a factor of x.
    for n in (3..).step_by(2).take_while(|m| *m <= x) {
        if x % n == 0 {
            return n;
        }
    }

    return x;
}

// Returns true if the number is prime.
pub fn is_prime(n: u64) -> bool {
    if n <= 1 {
        return false;
    }

    first_factor(n) == n
}
```
