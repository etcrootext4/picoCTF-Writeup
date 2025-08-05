# Fixme1.py picoCTF Write-Up

## Challenge Description
We are given a Python script named `fixme1.py`, but when attempting to run it, we encounter an **IndentationError**. Our task is to correct the indentation issues in the script so that it runs correctly and reveals the flag.

## Solution Steps

### 1. **Downloading the Script**
First, we download the provided script using `wget`:
```sh
wget https://artifacts.picoctf.net/c/25/fixme1.py
```

Once downloaded, we verify its presence using:
```sh
ls
```
Expected output:
```
README.txt  fixme1.py
```

### 2. **Running the Script**
Executing the script with Python:
```sh
python fixme1.py
```
Error output:
```
  File "fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
```
This indicates that there is an **indentation issue** at line 20.

### 3. **Fixing the Indentation**
We open the script in a text editor:
```sh
nano fixme1.py
```
Inside, we locate the faulty indentation and adjust it to maintain proper Python syntax. Specifically, we ensure that the `print()` statement aligns correctly with its preceding block.

### 4. **Running the Fixed Script**
After correcting the indentation, we save the file and execute it again:
```sh
python fixme1.py
```
Expected output:
```
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```

## Flag
```
picoCTF{1nd3nt1ty_cr1515_6a476c8f}
```