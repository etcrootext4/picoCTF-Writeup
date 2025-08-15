# EVEN RSA CAN BE BROKEN picoCTF Write-Up

## Challenge Description
This service provides you an encrypted flag. Can you decrypt it with just N & e?

## Solution Steps

- Connect to the challenge server:
  ```
  nc verbal-sleep.picoctf.net 55822
  ```
  You will receive:
  - N
  - e
  - ciphertext

- Analysis:
  - Normally, RSA modulus N = p * q.
  - In this challenge, N is even (N % 2 == 0), so p = 2 and N = 2 * q.
  - Euler's totient: φ(N) = (2-1)*(q-1) = q-1.
  - Calculate private exponent: d = inverse(e, φ).
  - Decrypt: plaintext = c^d mod N.

- Exploit code:
  ```python
  from Crypto.Util.number import inverse, long_to_bytes

  N = <N from server>
  e = 65537
  c = <ciphertext from server>

  p = 2
  q = N // p
  phi = q - 1
  d = inverse(e, phi)
  plaintext = long_to_bytes(pow(c, d, N)).decode()
  print(plaintext)
  ```

- The program prints the flag.

## Flag
```
picoCTF{tw0_1$_pr!m3f995d086}
```