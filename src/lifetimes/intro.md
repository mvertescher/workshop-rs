# Introduction

The term _lifetime_ is synonymous with scope for which a __reference__ is
valid.

Every reference in Rust has a lifetime.

Similar to types, Rust can infer the lifetimes of references in most cases.

In some situations, however, we must annotate lifetimes when it is unclear how
lifetimes are related.

> The concept of lifetimes is somewhat different from tools in other
> programming languages, arguably making lifetimes Rust’s most distinctive
> feature.
