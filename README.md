A macro that makes it easy to mock [todo](https://doc.rust-lang.org/std/macro.todo.html) with
values to make the code compilable.

The macro has two features:
- `todo`: works like a normal [todo](https://doc.rust-lang.org/std/macro.todo.html).
- `mock`: returns the mock value we provide.

# Installation
```toml
[dependencies]
mock_todo = { version = "0.1.0", features = ["mock"] }
# use the following commented line if you want to use a regular todo.
# mock_todo = { version = "0.1.0", features = ["todo"] }
```

# Example of usage
```rust
use mock_todo::mock_todo;
// returns 0 if the feature is "mock" and panics with the message "not yet implemented: Add feature" otherwise.
fn feature() -> u32 {
    // first argument can be ommited.
    mock_todo!("Add feature", 0)
}
```
