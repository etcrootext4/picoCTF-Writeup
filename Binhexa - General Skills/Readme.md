# binhexa picoCTF Write-Up

## Challenge Description
You are given a binary challenge where you must perform a series of bitwise and arithmetic operations on two binary numbers and provide the results in binary and hexadecimal to receive the flag.

## Solution Steps

- Connect to the challenge server:
  ```
  nc titan.picoctf.net 64992
  ```
- The server provides two binary numbers:
  - Binary Number 1: `01000011`
  - Binary Number 2: `00110101`

- Perform the following operations in order:

  1. **Multiplication (`*`)**
     ```
     01000011 * 00110101 = 110111011111
     ```
  2. **Bitwise AND (`&`)**
     ```
     01000011 & 00110101 = 00000001
     ```
  3. **Left Shift (`<<`)**
     ```
     01000011 << 1 = 10000110
     ```
  4. **Bitwise OR (`|`)**
     ```
     01000011 | 00110101 = 01110111
     ```
  5. **Addition (`+`)**
     ```
     01000011 + 00110101 = 1111000
     ```
  6. **Right Shift (`>>`)**
     ```
     00110101 >> 1 = 00011010
     ```
     Enter the result in hexadecimal: `1A`

- After entering all correct answers, the server returns the flag.

## Flag
```
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6ab1ad84}
```