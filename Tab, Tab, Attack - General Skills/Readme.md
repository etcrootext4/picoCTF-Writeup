# Tab, Tab, Attack picoCTF Write-Up

## Challenge Description
This challenge involves extracting hidden data from a deeply nested archive. The goal is to navigate through the file structure and extract the flag from a binary file.

## Solution Steps

1. **Download the ZIP File**  
   First, we download the challenge file using `wget`:
   ```bash
   wget https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip
   ```
   The file is successfully saved as `Addadshashanammu.zip`.

2. **Extract the ZIP File**  
   We extract the archive using `unzip`:
   ```bash
   unzip Addadshashanammu.zip
   ```
   This creates a deeply nested directory structure.

3. **Navigate the Directory Structure**  
   We explore the directories using `ls` and `cd`:
   ```bash
   cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
   ```
   Inside, we find a file named `fang-of-haynekhtnamet`.

4. **Inspect the File**  
   Using `cat`, we attempt to read the file:
   ```bash
   cat fang-of-haynekhtnamet
   ```
   The output contains unreadable binary data, but also a readable flag:
   ```
   picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
   ```

## Flag
```
picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```