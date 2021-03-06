# `panic!` Backtrace

Take this example of a [_buffer
over-read_](https://cwe.mitre.org/data/definitions/126.html):

```rust,should_panic,panics
fn main() {
    let v = vec![1, 2, 3];

    v[99];
}
```

In C, the compiler would _naively_ allow you to fetch index 99 with no
questions. This would be a security vulnerability that could be exploited.

In Rust, this triggers a `panic!` in the Standard Library.

We can set the `RUST_BACKTRACE` environment variable to uncover the source of
the `panic!`.
