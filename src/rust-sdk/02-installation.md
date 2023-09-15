# Installing the library

Add the `smartvaults-sdk` dependency in your `Cargo.toml` file:

```toml
[dependencies]
smartvaults-sdk = { git = "https://github.com/smartvaults/smartvaults", tag = "vX.X.X" }
```

Note: you can specify a commit using `rev` instead of `tag`.

## Examples

Use a specific version:

```toml
[dependencies]
smartvaults-sdk = { git = "https://github.com/smartvaults/smartvaults", tag = "v0.3.0" }
```

Use a specific commit:

```toml
[dependencies]
smartvaults-sdk = { git = "https://github.com/smartvaults/smartvaults", rev = "383c186cb1df3ab5906978d6b313aed86d2698b1" }
```