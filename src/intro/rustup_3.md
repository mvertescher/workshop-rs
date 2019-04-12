# Rustup

You can switch between complier releases with `rustup default`.

```sh
$ rustup default nightly
```

```plaintext
info: using existing install for 'nightly-x86_64-unknown-linux-gnu'
info: default toolchain set to 'nightly-x86_64-unknown-linux-gnu'

  nightly-x86_64-unknown-linux-gnu unchanged - rustc 1.34.0-nightly (f6fac4225 2019-02-03)
```

```sh
$ rustup default stable
```

```plaintext
info: using existing install for 'stable-x86_64-unknown-linux-gnu'
info: default toolchain set to 'stable-x86_64-unknown-linux-gnu'

  stable-x86_64-unknown-linux-gnu unchanged - rustc 1.32.0 (9fda7c223 2019-01-16)
```
