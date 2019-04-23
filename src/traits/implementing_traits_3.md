# Implementing Traits

If we wanted to implement an external trait on our local type, we would need to
bring the trait into scope first.

Alternatively, we could implement a local trait on an external type.

But, we _cannot_ implement external traits on external types.

This restriction is part of a property of programs called _coherence_,
specifically, the _orphan rule_, that ensures you cannot break other peoples
code and vice-versa.

Without this rule, two crates could implement the same trait for the same type,
and Rust would not know which implementation to use.
