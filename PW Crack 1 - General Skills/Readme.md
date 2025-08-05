# PW Crack 1 picoCTF Write-Up

## Challenge Description
This challenge provides a Python script (`level1.py`) that prompts the user for a password to decrypt a flag file (`level1.flag.txt.enc`). Our objective is to analyze the script and retrieve the correct password to obtain the flag.

## Solution Steps

1. **Analyze the Given Script (`level1.py`)**  
   The script contains a function `level_1_pw_check()` that verifies the input password:
   ```python
   def level_1_pw_check():
       user_pw = input("Please enter correct password for flag: ")
       if( user_pw == "8713"):
           print("Welcome back... your flag, user:")
           decryption = str_xor(flag_enc.decode(), user_pw)
           print(decryption)
           return
       print("That password is incorrect")
   ```
   From this, we see that the correct password is explicitly stated as **"8713"**.

2. **Run the Script with the Password**  
   We execute the script and enter the discovered password:
   ```bash
   Art1cx-picoctf@webshell:~$ python3 level1.py
   Please enter correct password for flag: 8713
   Welcome back... your flag, user:
   picoCTF{545h_r1ng1ng_1b2fd683}
   ```
   The script successfully decrypts and prints the flag.

## Flag
```
picoCTF{545h_r1ng1ng_1b2fd683}
```