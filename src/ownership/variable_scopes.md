# Variable Scopes

An example of _ownership_:

```rust,ignore
{ // s is not valid here, it’s not yet declared
  let s = "hey";  // s is valid from this point forward
  // do stuff with s
} // this scope is now over, and s is no longer valid
```
