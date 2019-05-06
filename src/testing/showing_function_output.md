# Showing Function Output

`cargo test` captures standard output.

Anything we print using `println!` for example, will not be displayed when
running tests.

We can disable standard output capture:

```sh
$ cargo test -- --nocapture
```
