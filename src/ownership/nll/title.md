# Briefly: Non-Lexical Lifetimes

Non-Lexical Lifetimes (NLL) was a recent change in the Rust compiler to make
the borrow checker more correct.

Lifetimes are now based on the control flow graph rather than lexical scopes.

Some of the borrow checker examples that previously did not compile, are now
ok!
