# endianness picoCTF Write-Up

## Challenge Description
You are given a word and must provide both its little endian and big endian hexadecimal representations to receive the flag.

## Solution Steps

- Connect to the challenge server:
  ```
  nc titan.picoctf.net 49591
  ```
- The server gives a word, for example: `zyhid`.
- Convert the word to its ASCII hex values:
  - `z` = 7a
  - `y` = 79
  - `h` = 68
  - `i` = 69
  - `d` = 64
- For **Little Endian**, reverse the order:
  ```
  646968797a
  ```
- For **Big Endian**, keep the original order:
  ```
  7a79686964
  ```
- Enter both representations when prompted.
- The server returns the flag.

## Flag
```
picoCTF{3ndi4n_sw4p_su33ess_cfe38ef0}
```