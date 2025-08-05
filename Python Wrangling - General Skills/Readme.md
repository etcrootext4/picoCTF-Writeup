# Python Wrangling picoCTF Write-Up

## Challenge Description
This challenge provides an encrypted flag file `flag.txt.en`, a Python script `ende.py`, and a password file `pw.txt`. The goal is to decrypt the encrypted file using the given script and password to obtain the flag.

## Solution Steps

1. **Inspect the Files**  
   List the contents of the directory:
   ```bash
   ls
   ```
   Output:
   ```
   README.txt  ende.py  flag.txt.en  pw.txt
   ```

2. **Check Encrypted Flag**  
   View the contents of the encrypted file:
   ```bash
   cat flag.txt.en
   ```
   Output:
   ```
   gAAAAABgUAIWuksW6PU7W1WFXiBWkF2S8VhtL_5335iazHhuBnWloiyt3ZAFwR2zyuG7iZLSVPaQIZLTxgo-WXIk6Cnk7-KZm1g1qo_v1zDMK5wDocmVFxL0o5ae6OrB9VKdh3HerIsy
   ```

3. **Check the Password File**  
   View the contents of `pw.txt`:
   ```bash
   cat pw.txt
   ```
   Output:
   ```
   dbd1bea4dbd1bea4dbd1bea4dbd1bea4
   ```

4. **Understand the Python Script**  
   Running the script without parameters shows its usage:
   ```bash
   python ende.py
   ```
   Output:
   ```
   Usage: ende.py (-e/-d) [file]
   ```
   The `-d` option is used for decryption.

5. **Decrypt the Flag**  
   Use the script with the `-d` option and provide the password when prompted:
   ```bash
   python ende.py -d flag.txt.en
   ```
   Input the password:
   ```
   dbd1bea4dbd1bea4dbd1bea4dbd1bea4
   ```
   Output:
   ```
   picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}
   ```

## Flag
```
picoCTF{4p0110_1n_7h3_h0us3_dbd1bea4}
```

