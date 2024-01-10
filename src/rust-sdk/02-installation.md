# Installing the library

<custom-tabs category="lang">
<div slot="title">Rust</div>
<section>

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

</section>

<div slot="title">Kotlin</div>
<section>

To use the Kotlin language bindings for `smartvaults-sdk` in your Android project add the following to your gradle dependencies:

```kotlin
repositories {
    mavenCentral()
}

dependencies { 
    implementation("io.smartvaults:smartvaults-sdk:<version>")
}
```

Import the library in your code:

```kotlin
import io.smartvaults.sdk.*
```

To import nostr or nostr-sdk:
```kotlin
import rust.nostr.protocol.*
import rust.nostr.sdk.*
```

## Known issues

### JNA dependency

Depending on the JVM version you use, you might not have the JNA dependency on your classpath. The exception thrown will be

```bash
class file for com.sun.jna.Pointer not found
```

The solution is to add JNA as a dependency like so:

```kotlin
dependencies {
    // ...
    implementation("net.java.dev.jna:jna:5.12.1")
}
```

</section>
</custom-tabs>