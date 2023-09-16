# Keychain

This section will show you how to manage the `keychain`.

## Definition

Keychain means a `seed` plus an optional list of `passphrases`.

## Store

The `keychian` it's stored in a file called `keechain`. It's encrypted using AES-256 in CBC mode and XChaCha20Poly1305: `XChaCha20Poly1305(AES256CBC(keychain))`.