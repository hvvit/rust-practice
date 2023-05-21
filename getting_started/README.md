
# Getting Started

## Hello World Program

following is the hello world program.

```rust
fn main() {
    println("Hello world")
}

```
compile the program with rustc command.
suppose the file is saved as 1_2_helloworld.rs, where .rs is the file extension for rust code.

to compile and run the rust code, use the below example.

```bash
rustc 1_2_helloworld.rs
./1_2_helloworld
```

it should printout hello, world in console.

### Understanding the rust code

understing the main block

```rust
fn main() {

}
```

This is main function, it is always the first code that runs in every executable rust program. Here, the first line declars a function named main that has no paramaters and returns nothing. If there were parameters, they would go inside the parantheses().

The function body is wrapped in {}. RUst requires curly bracket on the same line as the function declaration, adding one space in between.


The body of the main function holds the following code:

```rust
    println!("Hello, world!");
```

rust style is to indent with four spaces, not a tab.

second, println! calls a Rust macro. If it had called a function instead, it would be entered as println without the !. we will se rust macros in more detail later on. For now when we call any funciton with ! its called a macro, instead of a function.

## Cargo

cargo is rust's build system and package manager, just like how python has pip3, nodejs has npm the same way rust has cargo.
cargo handles a lot of tasks, such as building code, downloading libs that my program depends on and building those libraries.

cargo comes installed with rust.
to check the version of cargo, run the following command
```bash
[harshvardhan@fedora getting_started]$ cargo --version
cargo 1.69.0 (6e9a83356 2023-04-12)
```

### Creating a new project with Cargo

To create new project with cargo, trigger the following command.

```bash
cargo new hello_cargo
```

the first command creates a new directory and project called hello_cargo. We've named our project hello_cargo, and Cargo creates its files in a directory of the same name.

Cargo has generated two files and a directory, a Cargo.toml file and a src directory with main.rs file inside.

It has also initialised a new git repo along with a .gitignore file. Gir files won't be generated if you run cargo new withing an existing Git repo, you can override this behaviour by using cargo new --vcs=git.

Cargo.toml consists of the following
```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```
cargo source files should be inside the src directory

to build the cargo project run the following command

```bash
[harshvardhan@fedora hello_cargo]$ cargo build
Compiling hello_cargo v0.1.0 (/home/harshvardhan/git/rust-practice/getting_started/hello_cargo)
 Finished dev [unoptimized + debuginfo] target(s) in 0.45s
```

this command builds an executable file in target/debug/hello_cargo. because default build is a debug build, Cargo puts the binary in a directory named debug. You  can run executable with this command:

```bash
[harshvardhan@fedora hello_cargo]$ ./target/debug/
build/        deps/         examples/     .fingerprint/ hello_cargo   incremental/  
[harshvardhan@fedora hello_cargo]$ ./target/debug/hello_cargo 
Hello, world!
```