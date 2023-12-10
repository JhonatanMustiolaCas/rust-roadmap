
#Rust 

[Language basics](Rust.md#Language%20basics)

---
# Variables, Constants, and Data Types

In Rust, variables are declared using the `let` keyword. They are immutable by default, which means once a value is bound to a variable, it cannot be changed. If you want to make a variable mutable, the `mut` keyword is used. So, if you wanted to declare a mutable variable `x` and assign it the value `5`, you would write `let mut x = 5;`. Variables can also be patterned. By default in Rust, variables are block-scoped. Rust also supports several types of variable attributes.

A set of variables can be declared in one line, like so
```rust
let (mut x, y, z);
```

---
## Variables

**A variable cannot be used if it isn't initialised**

```rust
fn main() {
	let x: i32;
	let y: i32;

	assert_eq!(x, 5); // Error
	println!("Success");
}
```

Referring to the example above, for uninitialised and unused variables there'd be only warnings. ==For avoiding warnings, it's allowed to prepend an underscore to the variable identifier== like so `let _y: i32`.

Another way to avoiding this warning is adding 
`#[allow(unused_variables)]` at the very top of the file

<br>
`let` keyword is used for declaring variables. But declared variables are immutable by default, so their values cannot be changed once initialised. For setting the variables in order to be mutable, the `mut` keyword is added within the declaration, as below
```rust
fn main() {
	let immutable_int: i32; // immutable by default
	let mut mutable_int: i32; // declared as mutable
}
```

```rust
fn main() {
	let mut x = 1;
	x += 2;

	assert_eq!(x, 3);
	println!("Success");
}
```

<br>
The scope of a variable is the levelled code-block where a variable can be used and recognised by other functions and operations

```rust
//outer scope

let x_3: i32 = 5;
let y_3: i32 = 6;

{ //inner scope
	// let y_3: i32 = 6; it'd cause an error when printing from the outer scope
	println!("The value of x_3 is {} and value of y_3 is {}", x_3, y_3);
}
println!("The value of x_3 is {} and value of y_3 is {}\n", x_3, y_3);

```

<br>
In Rust, shadowing is allowed when a variable in a scope is declared with the same identifier as the outer/inner scoped one,or even the main function scope. In this case, it is possible to use each variable only with the operations performed in the scope that they are *"attached"* in

```rust
let x_4: i32 = 5;
{
	let x_4 = 12;
	assert_eq!(x_4, 12);
}

assert_eq!(x_4, 5);

let x_4: i32 = 42;
println!("{}\n", x_4); // output: 42
```
