# Rust fixme 1 picoCTF Write-Up

## Challenge Description
You are given a Rust project with a broken main.rs file. Your task is to fix the code so it compiles and reveals the flag.

## Solution Steps

- Extract the provided `fixme1.tar.gz` archive. You will find:
  - `Cargo.lock`
  - `Cargo.toml`
  - `src/main.rs`
- Open `src/main.rs` and fix the following issues:
  1. Add a semicolon (`;`) after the key declaration.
  2. Change `ret;` to `return;` for proper Rust syntax.
  3. Update the `println!` macro to use the `{}` placeholder for printing variables.
- After fixing the code, build and run the project:
  ```
  cargo run
  ```
- The program will output the flag.

## Flag
```
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```