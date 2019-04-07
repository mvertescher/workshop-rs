# To `panic!` or Not to `panic!`

Sometimes, it is ok to `panic!`:

- Examples, prototypes, tests
- When you have more information than the compiler:
  ```rust
  use std::net::IpAddr;

  let home: IpAddr = "127.0.0.1".parse().unwrap()
  ```
- Your binary will end up in an unrecoverable bad state
- Your library is being misused and the calling programmers need to fix their code

In all other cases, it is preferable to return a `Result`.
