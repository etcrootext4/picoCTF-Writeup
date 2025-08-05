# PW Crack 2 picoCTF Write-Up

## Challenge Description

This challenge provides a Python script (`level2.py`) that prompts the user for a password to decrypt a flag file (`level2.flag.txt.enc`). The hint suggests that we do not need to reverse-engineer the `str_xor` function, meaning our primary focus should be finding the correct password.

## Solution Steps

1. **Analyze the Given Script (********`level2.py`********)**\
   The script includes a function called `level_2_pw_check()` that verifies the input password:

   ```python
   def level_2_pw_check():
       user_pw = input("Please enter correct password for flag: ")
       if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
           print("Welcome back... your flag, user:")
           decryption = str_xor(flag_enc.decode(), user_pw)
           print(decryption)
           return
       print("That password is incorrect")
   ```

   The password is constructed using the `chr()` function with hexadecimal values:

   ```python
   chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39)
   ```

   Converting these values to ASCII:

   - `0x34` → `'4'`
   - `0x65` → `'e'`
   - `0x63` → `'c'`
   - `0x39` → `'9'`

   Thus, the password is **"4ec9"**.

2. **Run the Script with the Password**\
   We execute the script and enter the discovered password:

   ```bash
   Art1cx-picoctf@webshell:~$ python3 level2.py
   Please enter correct password for flag: 4ec9
   Welcome back... your flag, user:
   picoCTF{tr45h_51ng1ng_9701e681}
   ```

   The script automatically decrypts and prints the flag.

## Flag

```
picoCTF{tr45h_51ng1ng_9701e681}
```