# Preventing Dangling References

The primary goal of lifetimes is to prevent dangling references.

Let's look at an example:

```rust,ignore
{
    let r;

    {
        let x = 5;
        r = &x;
    }

    println!("r: {}", r);
}
```

`r` is assigned to a reference to `x`, but `x` "does not live long enough":

```plaintext
error[E0597]: `x` does not live long enough
  --> src/main.rs:9:14
   |
9  |         r = &x;
   |              ^ borrowed value does not live long enough
10 |     }
   |     - `x` dropped here while still borrowed
...
13 | }
   | - borrowed value needs to live until here
```

How does Rust determine that this code is invalid? __The Borrow Checker__.
