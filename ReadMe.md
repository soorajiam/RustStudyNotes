# Learn RUST

Author: https://www.udemy.com/user/lyubomir-gavadinov/
Link: https://www.udemy.com/course/rust-fundamentals/learn/lecture/
Publisher: Udemy
Related to Tag (Column): https://www.notion.so/RUST-d8ad452fef014a5cbe4ab06627839f1e
Status: Watching
Summary: In this course you will learn the fundamentals of Rust. The format will be a bit different than most other courses. Instead of jumping between unrelated concepts in every video and showing examples that have nothing to do with the real world use of the language, we will learn entirely through practice
Type: rust
completion percent: <10%
expiry: February 26, 2023

# References

[The Rust Programming Language - The Rust Programming Language](https://doc.rust-lang.org/book/title-page.html)

[](https://www.udemy.com/course/rust-fundamentals/learn/lecture/)

# Stack and Heaps

> write notes on heap and stack
> 

Allocated memory is from heap. The allocated variable will have pointer to heap storage in stack.

If allocated, it should be deallocated.

smart pointer - added functionalities on-top of raw pointer. usually deallocates memory when the program goes out of range.

# Basic data types

## Integers

memory size

- 8
- 16
- 32
- 64
- 128

and type

- Unsigned(u)
- signed(i)

OR

## usize, isize

Architecture dependant

32bit size on 32-bit architecture

64 in 64 bit architecture

## Floating point

f32 - 32 bit

f64 - 64 bit

## Boolean

bool - 1 bit

## Char

- single unicode value - 4 bits
- if we are using ascii - we might be wasting memory

# Running program

**file format :** `.rs`

Before running a Rust program, you must compile it using the Rust compiler by entering the `rustc`
 command and passing it the name of your source file, like this:

**compiling:** `rustc filename.rs`

On Linux, macOS, and PowerShell on Windows, you can see the executable by entering the `ls`
 command in your shell:

**running:** .`/filename`

# Main Function

These lines define a function named `main`. The `main` function is special: it is always the first code that runs in every executable Rust program. Here, the first line declares a function named `main` that has no parameters and returns nothing. If there were parameters, they would go inside the parentheses `()`.

The function body is wrapped in `{}`. Rust requires curly brackets around all function bodies. It’s good style to place the opening curly bracket on the same line as the function declaration, adding one space in between.

```rust
fn main() {

}
```

> First, Rust style is to indent with four spaces, not a tab.
> 

# Cargo

- We can create a project using `cargo new`.
- We can build a project using `cargo build`.
- We can build and run a project in one step using `cargo run`.
- We can build a project without producing a binary to check for errors using `cargo check`.
- Instead of saving the result of the build in the same directory as our code, Cargo stores it in the *target/debug* directory.

Cargo is Rust’s build system and package manager. Most Rustaceans use this tool to manage their Rust projects because Cargo handles a lot of tasks for you, such as building your code, downloading the libraries your code depends on, and building those libraries.

```rust
$ cargo --version
```

## creating project

```rust
$ cargo new hello_cargo
$ cd hello_cargo
```

generated two files and one directory for us: a *Cargo.toml* file and a *src* directory with a *main.rs* file inside.

It has also initialized a new Git repository along with a *.gitignore* file. Git files won’t be generated if you run `cargo new` within an existing Git repository; you can override this behavior by using `cargo new --vcs=git`.

## building project with cargo

```rust
cargo build
```

This command creates an executable file in *target/debug/hello_cargo*
 (or *target\debug\hello_cargo.exe*
 on Windows) rather than in your current directory. Because the default build is a debug build, Cargo puts the binary in a directory named *debug*
. You can run the executable with this command:

```rust
$ ./target/debug/hello_cargo # or .\target\debug\hello_cargo.exe on Windows
Hello, world!
```

## Running code

We just built a project with `cargo build`
 and ran it with `./target/debug/hello_cargo`
, but we can also use `cargo run`
 to compile the code and then run the resultant executable all in one command:

```rust
cargo run
```

Using `cargo run`is more convenient than having to remember to run `cargo build`
 and then use the whole path to the binary, so most developers use `cargo run`.

## Cargo check

Cargo also provides a command called `cargo check`. This command quickly checks your code to make sure it compiles but doesn’t produce an executable:

```rust
cargo check
```

## **[Building for Release](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html#building-for-release)**

`cargo build --release`
 to compile it with optimizations. This command will create an executable in *target/release*