# Mutable References

You can only have 1 mutable reference at a time!

This restriction helps prevent _data races_ at compile time!

The benefit of having this restriction is that Rust can prevent data races at
compile time. A data race is similar to a race condition and happens when these
three behaviors occur:

- Two or more pointers access the same data at the same time.
- At least one of the pointers is being used to write to the data.
- There’s no mechanism being used to synchronize access to the data.
