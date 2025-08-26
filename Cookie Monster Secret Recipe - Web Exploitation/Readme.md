# Cookie Monster Secret Recipe picoCTF Write-Up

## Challenge Description
You are given a website that checks for a special cookie value. Your goal is to find and decode the secret hidden in the cookie.

## Solution Steps

- Visit the challenge website and inspect the cookies.
- Find a cookie value:
  ```
  cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc4QjRDMzkwfQ%3D%3D
  ```
- Decode the value from URL encoding and then base64:
  - URL decode: `cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzc4QjRDMzkwfQ==`
  - Base64 decode: `picoCTF{c00k1e_m0nster_l0ves_c00kies_78B4C390}`

## Flag
```
picoCTF{c00k1e_m0nster_l0ves_c00kies_78B4C390}
```