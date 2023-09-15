# Features

The Rust SDK can be used both in `async/await` and `blocking` contexts.

By default, the SDK operate in `async` mode, so to use it in a blocking context, you have to specify the `blocking` feature:

```toml
[dependencies]
smartvaults-sdk = { ..., features = ["blocking"] }
```