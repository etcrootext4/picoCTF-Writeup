# Rust fixme 2 picoCTF Write-Up

## Challenge Description
You are given a Rust project with a main.rs file that needs fixing. The goal is to correct the code so it compiles and reveals the flag.

## Solution Steps

- Extract the provided `fixme2.tar.gz` archive. You will find:
  - `Cargo.lock`
  - `Cargo.toml`
  - `src/main.rs`
- Open `src/main.rs` and fix the following issues:
  1. To mutate a string inside a function, pass it as `&mut String` in the function parameter.
  2. Declare the variable `party_foul` as `mut` so it can be borrowed as mutable.
  3. Call the function with `&mut party_foul` to allow changes.
- After fixing the code, build and run the project:
  ```
  cargo run
  ```
- The program will output the flag.

## Flag
```
picoCTF{4r3_y0u_h4v1n5_fun_y31?}
```