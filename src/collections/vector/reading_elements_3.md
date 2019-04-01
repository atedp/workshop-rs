# Reading Elements

What happens when we reference a vector element and then try to modify the
vector?

```rust,ignore,does_not_compile
let mut v = vec![1, 2, 3, 4, 5];

let first = &v[0];

v.push(6);

println!("The first element is: {}", first);
```