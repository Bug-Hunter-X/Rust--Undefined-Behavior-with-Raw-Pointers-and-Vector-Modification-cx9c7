# Rust Undefined Behavior Example

This repository demonstrates a common source of undefined behavior in Rust: modifying a vector's contents through a raw pointer after the vector's length or capacity has changed.  Modifying memory through raw pointers after the underlying data has been moved or reallocated will often result in crashes or unpredictable results.  This is important to understand when working with low-level operations in Rust.

## Bug Description

The `bug.rs` file contains code that attempts to modify a vector using a raw pointer obtained via `as_mut_ptr()`. After this, the vector's contents are changed. This can lead to unexpected behavior and crashes.