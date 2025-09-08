# Super SSH picoCTF Write-Up

## Challenge Description
Using a Secure Shell (SSH) is going to be pretty important.  
Can you ssh as ctf-player to titan.picoctf.net at port 62837 to get the flag?  
You'll also need the password `83dcefb7`. If asked, accept the fingerprint with yes.

## Solution Steps

- Connect to the server using SSH:
  ```
  ssh ctf-player@titan.picoctf.net -p 62837
  ```
- Enter the password when prompted: `83dcefb7`
- Accept the fingerprint if asked by typing `yes`.
- Upon successful login, the flag is displayed.

## Flag
```
picoCTF{s3cur3_c0nn3ct10n_8969f7d3}
```