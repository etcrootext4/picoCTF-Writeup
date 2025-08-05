# Interencdec picoCTF Write-Up

## Challenge Description
This challenge provides a Base64-encoded string with the hint: "Engaging in various decoding processes is of utmost importance." This suggests that multiple layers of encoding need to be decoded to retrieve the flag.

## Solution Steps

1. **Decode the Given Base64 String**  
   The given string:
   ```
   YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6ZzJhMnd6TW1zeWZRPT0nCg==
   ```
   Decoding this from Base64 yields another Base64-encoded string:
   ```
   d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzg2a2wzMmsyfQ==
   ```

2. **Decode the Second Base64 String**  
   Decoding this second layer reveals:
   ```
   wpjvJAM{jhlzhy_k3jy9wa3k_86kl32k2}
   ```
   This resembles a flag format but appears to be encoded further.

3. **Apply Caesar Cipher Decryption**  
   Observing the text, it seems that a **Caesar cipher** shift might have been applied. Using a brute-force approach, we try different shifts and find that a shift of **7** gives:
   ```
   picoCTF{caesar_d3cr9pt3d_86de32d2}
   ```

## Flag
```
picoCTF{caesar_d3cr9pt3d_86de32d2}
```

