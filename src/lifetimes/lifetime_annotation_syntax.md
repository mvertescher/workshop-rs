# Lifetime Annotation Syntax

Just like how functions can accept generic type parameters, functions can also
accept _generic lifetime parameters_.

_Generic lifetime parameters_ don't change how long references live, but rather
describe the relationship of multiple references.

Lifetime annotations always start with an apostrophe (`'`) and are usually all
lower case and very short, like generic types.

We place the lifetime annotation after the `&` of a reference and use a space to
separate the annotation from the reference type.

Here are some examples:

```rust,ignore
&i32        // a reference
&'a i32     // a reference with an explicit lifetime
&'a mut i32 // a mutable reference with an explicit lifetime
```
