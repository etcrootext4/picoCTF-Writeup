# hashcrack picoCTF Write-Up

## Challenge Description
In this challenge, you are given access to a remote server via netcat and must crack several hashes to reveal the flag.  
You will use online hash cracking tools to identify the plaintext for each hash provided by the server.

## Solution Steps

1. **Connect to the Server**  
   Use netcat to connect to the challenge server:
   ```
   nc verbal-sleep.picoctf.net 57192
   ```
   The server will prompt you with a hash to crack.

2. **Crack the MD5 Hash**  
   The first hash provided is:
   ```
   482c811da5d5b4bc6d497ffa98491e38
   ```
   Use an online hash cracker such as [crackstation.net](https://crackstation.net/) to find the plaintext:
   ```
   password123
   ```
   Enter this password into the server prompt.

3. **Crack the SHA-1 Hash**  
   The next hash is:
   ```
   b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
   ```
   Use the same online tool to find the plaintext:
   ```
   letmein
   ```
   Enter this password into the server prompt.

4. **Crack the SHA-256 Hash**  
   The final hash is:
   ```
   916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
   ```
   Use the online tool to find the plaintext:
   ```
   qwerty098
   ```
   Enter this password into the server prompt.  
   The server will reveal the flag.

## Flag
```
picoCTF{UseStr0nG_h@shEs_&PaSswDs!_29028be8}
```