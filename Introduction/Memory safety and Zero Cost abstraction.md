
#Rust 

[Introduction](Rust.md#Introduction)

---
# Memory Safety and Zero-Cost Abstractions

Rust, a systems programming language that runs blazingly fast, prevents segfaults, and guarantees thread safety. It is graced with the feature of “memory safety without garbage collection”, an attribute that makes Rust one of its kind. Memory safety is ensuring that software, while accessing the system’s memory, is not causing any leaks, or dangling pointers. In Rust, memory safety is accomplished through a system of ownership with a set of rules that the compiler checks at compile time. This system eliminates the need of garbage collection or manual memory management, hence ensuring swift execution of software along with a safer memory environment. This memory management feature in Rust even provides concurrent programming guaranteeing thread safety with options for shared and mutable state access that makes it harder to cause thread unsafety.