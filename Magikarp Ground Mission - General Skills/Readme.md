# Magikarp Ground Mission picoCTF Write-Up

## Challenge Description
This challenge involves connecting to a remote server via SSH and navigating the file system to retrieve parts of the flag. The goal is to follow the given hints and locate all three parts of the flag.

## Solution Steps

1. **Connect to the Remote Server**  
   Using the provided SSH command, connect to the challenge server:
   ```bash
   ssh ctf-player@venus.picoctf.net -p 52537
   ```
   Enter the password when prompted to gain access to the system.

2. **Locate the First Part of the Flag**  
   List the files in the home directory:
   ```bash
   ls
   ```
   We find a file named `1of3.flag.txt`. Viewing its contents:
   ```bash
   cat 1of3.flag.txt
   ```
   Output:
   ```
   picoCTF{xxsh_
   ```

3. **Follow Instructions to the Second Part**  
   The file `instructions-to-2of3.txt` suggests going to the root directory `/`:
   ```bash
   cd /
   ls
   ```
   Here, we find `2of3.flag.txt`. Viewing its contents:
   ```bash
   cat 2of3.flag.txt
   ```
   Output:
   ```
   0ut_0f_\/\/4t3r_
   ```

4. **Follow Instructions to the Final Part**  
   The `instructions-to-3of3.txt` file suggests returning to the home directory `~`:
   ```bash
   cd ~
   ls
   ```
   Here, we find `3of3.flag.txt`. Viewing its contents:
   ```bash
   cat 3of3.flag.txt
   ```
   Output:
   ```
   71be5264}
   ```

5. **Combine the Flag Parts**  
   Combining all three parts:
   ```
   picoCTF{xxsh_0ut_0f_\/\/4t3r_71be5264}
   ```

## Flag
```
picoCTF{xxsh_0ut_0f_\/\/4t3r_71be5264}
```