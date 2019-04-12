# Cargo New

Cargo new creates a new Rust package.

```sh
$ cargo new -h
```

```plaintext
cargo-new
Create a new cargo package at path

USAGE:
    cargo new [OPTIONS] path

OPTIONS:
        --registry  REGISTRY     Registry to use
        --vcs VCS                Initialize a new repository for the given version control system (git, hg, pijul, or
                                 fossil) or do not initialize any version control at all (none), overriding a global
                                 configuration. [possible values: git, hg, pijul, fossil, none]
        --bin                    Use a binary (application) template [default]
        --lib                    Use a library template
        --edition YEAR           Edition to set for the crate generated [possible values: 2015, 2018]
        --name NAME              Set the resulting package name, defaults to the directory name
    -v, --verbose                Use verbose output (-vv very verbose/build.rs output)
    -q, --quiet                  No output printed to stdout
        --color WHEN             Coloring: auto, always, never
        --frozen                 Require Cargo.lock and cache are up to date
        --locked                 Require Cargo.lock is up to date
    -Z  FLAG...                  Unstable (nightly-only) flags to Cargo, see 'cargo -Z help' for details
    -h, --help                   Prints help information
```
