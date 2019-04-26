# The Borrow Checker

The borrow checker is the part of the Rust compiler that compares scopes to
determine whether all borrows are valid.

Below, we've annotated the lifetimes, `'a` and `'b`, of the variables, `r` and
`x` respectively:

```rust,ignore
{
    let r;                // ---------+-- 'a
                          //          |
    {                     //          |
        let x = 5;        // -+-- 'b  |
        r = &x;           //  |       |
    }                     // -+       |
                          //          |
    println!("r: {}", r); //          |
}                         // ---------+
```

Since `r` refers to memory with a lifetime `'b`, which has a _shorter_ lifetime
than `'a`, this program is rejected.

Let's fix this example by extending the lifetime of `x`, `'b`.

```plaintext
{
    let x = 5;            // ----------+-- 'b
                          //           |
    let r = &x;           // --+-- 'a  |
                          //   |       |
    println!("r: {}", r); //   |       |
                          // --+       |
}                         // ----------+
```

This is _where_ and _how_ Rust analyzes lifetimes.
