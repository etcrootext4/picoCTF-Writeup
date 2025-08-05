# DISKO 1 picoCTF Write-Up

## Challenge Description
This challenge provides a disk image file and asks us to find the hidden flag inside it.  
**Hint:** _Maybe Strings could help? If only there was a way to do that?_

To solve this challenge, we will explore the contents of the disk image using Linux command-line tools such as `gunzip`, `strings`, and `grep`.

## Solution Steps

1. **Extract the Disk Image**  
   The file provided is a gzip-compressed disk image (`disko-1.dd.gz`). First, we extract it using the `gunzip` command:
   ```bash
   gunzip disko-1.dd.gz
   ```

2. **Search for the Flag Using Strings and Grep**  
   Since the hint suggests using "Strings", we extract printable strings from the raw disk image using the `strings` command and filter them with `grep` to find the flag format (typically containing "pico"):
   ```bash
   strings disko-1.dd | grep pico
   ```
   Example output:
   ```
   picoCTF{1t5_ju5t_4_5tr1n9_c63b02ef}
   ```

## Flag
```
picoCTF{1t5_ju5t_4_5tr1n9_c63b02ef}
```